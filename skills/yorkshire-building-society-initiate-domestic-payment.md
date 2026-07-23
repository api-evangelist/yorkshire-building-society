---
name: Initiate a YBS domestic payment (PIS)
description: Create a domestic-payment consent, complete PSU authorisation, optionally check funds, then initiate a single immediate domestic payment idempotently.
api: openapi/yorkshire-building-society-payment-initiation-api-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a YBS domestic payment (PIS)

Use this to initiate a single immediate domestic (UK Faster Payments) payment from a consenting Yorkshire/Chelsea Building Society account under OBIE Read/Write v3.1.2. You must be an FCA-authorised PISP with a valid OBIE/eIDAS certificate.

## Prerequisites
- Mutual-TLS on every call; certificate-bound tokens; PS256 request objects.
- Sign payment write requests with a detached JWS in the `x-jws-signature` header.
- Send `x-idempotency-key` (max 40 chars) on every payment write — replaying the same key + identical body returns the original resource; a different body is rejected (`UK.OBIE.Rules.ResourceAlreadyExists`).

## Steps
1. Get a client-credentials token (`payments` scope) via `TPPOAuth2Security`.
2. `CreateDomesticPaymentConsents` — POST the `Initiation` (creditor account, `InstructedAmount`); capture `ConsentId`.
3. Redirect the PSU (`authorizationCode` / `PSUOAuth2Security`) with `openbanking_intent_id` = `ConsentId`; PSU completes SCA. Exchange the code for a PSU token.
4. `GetDomesticPaymentConsentsConsentId` — confirm status `Authorised`.
5. (Optional) `GetDomesticPaymentConsentsConsentIdFundsConfirmation` — confirm funds are available.
6. `CreateDomesticPayments` — POST the same `Initiation` plus the `ConsentId`, with `x-idempotency-key` and `x-jws-signature`; capture `DomesticPaymentId`.
7. `GetDomesticPaymentsDomesticPaymentId` — poll until the payment `Status` settles.

## Rules
- The `Initiation` in the payment must match the authorised consent exactly, or you get `UK.OBIE.Resource.ConsentMismatch`.
- Errors use the `OBErrorResponse1` envelope; log the `x-fapi-interaction-id`.
- Never retry a payment without the original `x-idempotency-key` — that is how OBIE prevents double payments.
