---
name: Retrieve YBS account and transaction data (AIS)
description: Set up an OBIE account-access consent, complete PSU authorisation, then read a consenting YBS/CBS customer's accounts, balances and transactions.
api: openapi/yorkshire-building-society-account-information-api-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountId, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Retrieve YBS account and transaction data (AIS)

Use this to read Account Information for a consenting Yorkshire Building Society or Chelsea Building Society payment-account customer under the OBIE Read/Write Standard v3.1.2. You must be an FCA-authorised AISP with a valid OBIE/eIDAS transport certificate.

## Prerequisites
- Onboard via Dynamic Client Registration and obtain client credentials.
- Every call goes over mutual-TLS; access tokens are certificate-bound.
- Discovery: `https://api.ybs.co.uk/open-banking/v1.0/.well-known/ybs/openid-configuration`.
- Send `x-fapi-interaction-id` on every request and retain it for support.

## Steps
1. Get a client-credentials token (`accounts` scope) from `https://ob-ybs.api.ybs.co.uk/identity/open-banking/v3.1/token` using `TPPOAuth2Security`.
2. `CreateAccountAccessConsents` — POST the requested `Permissions` and expiry; capture the returned `ConsentId`.
3. Redirect the PSU to the authorization endpoint (`authorizationCode` / `PSUOAuth2Security`) with the `openbanking_intent_id` set to the `ConsentId`; the PSU completes PSD2 strong customer authentication.
4. Exchange the returned authorization code for a PSU access token.
5. `GetAccountAccessConsentsConsentId` — confirm the consent status is `Authorised`.
6. `GetAccounts` — list the accounts the PSU consented to.
7. For an account, call `GetAccountsAccountId`, `GetAccountsAccountIdBalances`, and `GetAccountsAccountIdTransactions` (paginate via OBIE `Links.Next` / `Meta.TotalPages`).

## Rules
- Errors return the `OBErrorResponse1` envelope with `UK.OBIE.*` codes — surface `Id` (the interaction id) for support.
- A `403` means the token/consent lacks the permission; re-check the consent `Permissions`.
- Do not fabricate `AccountId`s; only ids returned by `GetAccounts` are valid.
