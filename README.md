# Yorkshire Building Society (yorkshire-building-society)

Yorkshire Building Society (YBS) is a UK mutual building society founded in 1864 and headquartered in Bradford, West Yorkshire. As a member-owned mutual - owned by and run for its savers and borrowers rather than external shareholders - the YBS Group serves more than three million customers with around £66 billion in assets across the Yorkshire Building Society, Chelsea Building Society (CBS), Norwich & Peterborough and Accord Mortgages brands. YBS is an FCA-authorised ASPSP and, although not one of the CMA9 banks mandated to build Open Banking, is a voluntary participant in the UK Open Banking / PSD2 ecosystem. It runs a public developer portal at developers.ybs.co.uk documenting its OBIE Read/Write API family, conformant to the Open Banking Implementation Entity (OBIE) Read/Write Data API Standard v3.1.2 and secured with FAPI-grade OAuth2/OIDC, PSD2 strong customer authentication and mutual-TLS.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/yorkshire-building-society/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/yorkshire-building-society/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Building Society
- Open Banking
- PSD2
- OBIE
- FAPI
- United Kingdom
- Payments
- Account Information
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Yorkshire Building Society Account Information API

OBIE Read/Write Account and Transaction Information (AISP) API v3.1.2 - account, balance, transaction, beneficiary, standing-order, direct-debit, product, party and statement data for consenting YBS and Chelsea Building Society customers.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/account-information-api](https://developers.ybs.co.uk/api-catalog/account-information-api)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/open-banking/v3.1/aisp`

#### Properties

- [OpenAPI](openapi/yorkshire-building-society-account-information-api-openapi.yaml) — OBIE shared standard v3.1.2 (not a bank-proprietary contract)
- [Documentation](https://developers.ybs.co.uk/api-catalog/account-information-api)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

### Yorkshire Building Society Payment Initiation API

OBIE Read/Write Payment Initiation (PISP) API v3.1.2 - domestic single, scheduled, standing-order and file payment consents and initiation from consenting YBS and Chelsea Building Society accounts.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/payment-initiation-api-0](https://developers.ybs.co.uk/api-catalog/payment-initiation-api-0)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/open-banking/v3.1/pisp`

#### Properties

- [OpenAPI](openapi/yorkshire-building-society-payment-initiation-api-openapi.yaml) — OBIE shared standard v3.1.2 (not a bank-proprietary contract)
- [Documentation](https://developers.ybs.co.uk/api-catalog/payment-initiation-api-0)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

### Yorkshire Building Society Confirmation of Funds API

OBIE Read/Write Confirmation of Funds (CBPII) API v3.1.2 - card-based payment instrument issuers confirm whether funds are available on a consenting YBS or Chelsea Building Society account.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/confirmation-funds-api](https://developers.ybs.co.uk/api-catalog/confirmation-funds-api)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/open-banking/v3.1/cbpii`

#### Properties

- [OpenAPI](openapi/yorkshire-building-society-confirmation-of-funds-api-openapi.yaml) — OBIE shared standard v3.1.2 (not a bank-proprietary contract)
- [Documentation](https://developers.ybs.co.uk/api-catalog/confirmation-funds-api)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

### Yorkshire Building Society Event Subscriptions API

OBIE Read/Write Event Subscriptions API v3.1.2 - create, read and delete event subscriptions for aggregated-polling and real-time event notifications on YBS and Chelsea Building Society Open Banking resources.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/event-subscriptions-api](https://developers.ybs.co.uk/api-catalog/event-subscriptions-api)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/open-banking/v3.1/aisp`

#### Properties

- [OpenAPI](openapi/yorkshire-building-society-event-subscriptions-api-openapi.yaml) — OBIE shared standard v3.1.2 (not a bank-proprietary contract)
- [Documentation](https://developers.ybs.co.uk/api-catalog/event-subscriptions-api)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

### Yorkshire Building Society Dynamic Client Registration API

OBIE Dynamic Client Registration (DCR) API v3.1 - register a TPP client application with the YBS and Chelsea Building Society authorization servers using an OBIE/eIDAS software statement. Part of the OBIE security profile.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/dynamic-client-registration-api-0](https://developers.ybs.co.uk/api-catalog/dynamic-client-registration-api-0)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/register`

#### Properties

- [Documentation](https://developers.ybs.co.uk/api-catalog/dynamic-client-registration-api-0)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

### Yorkshire Building Society Generate Access Token API

OBIE token endpoint (Generate Access Token API v3.1.0) - the OAuth2/OIDC token endpoint used by onboarded TPPs to obtain access tokens against the YBS and Chelsea Building Society authorization servers.

- **Human URL:** [https://developers.ybs.co.uk/api-catalog/generate-access-token-api](https://developers.ybs.co.uk/api-catalog/generate-access-token-api)
- **Base URL:** `https://ob-ybs.api.ybs.co.uk/token`

#### Properties

- [Documentation](https://developers.ybs.co.uk/api-catalog/generate-access-token-api)
- [Getting Started](https://developers.ybs.co.uk/docs/getting-started)

## Common Properties

- [Website](https://www.ybs.co.uk/)
- [Developer Portal](https://developers.ybs.co.uk/)
- [Documentation](https://developers.ybs.co.uk/docs/getting-started)
- [Support](https://developers.ybs.co.uk/support)
- [Terms of Service](https://developers.ybs.co.uk/legal)
- [Privacy Policy](https://developers.ybs.co.uk/privacy-policy)
- [LinkedIn](https://www.linkedin.com/company/yorkshire-building-society)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
