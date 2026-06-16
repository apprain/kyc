# Quick Start

This guide demonstrates how to integrate Apprain KYC using the sandbox environment.

## Sandbox Environment

Base URL:

```
https://kyc.apprain.ca
```

Sandbox Credentials:

```
Client ID:
app_43bfa1bacf4435bfc2405459

Client Secret:
secret_75f1d4deec9274c35c65a8744146d5406e19d167e8d3f
```

> These credentials are for testing purposes only.

---

## Step 1: Create a KYC Session

Request:

```bash
curl --location 'https://kyc.apprain.ca/api/v1/kyc/sessions' \
--header 'Content-Type: application/json' \
--header 'x-client-id: app_43bfa1bacf4435bfc2405459' \
--header 'x-client-secret: secret_75f1d4deec9274c35c65a8744146d5406e19d167e8d3f' \
--data '{
  "externalUserId": "USER-1001",
  "redirectUrl": "https://localhost/kyc/callback"
}'
```

Request Fields:

| Field | Description |
|---------|-------------|
| externalUserId | Unique identifier from the client application |
| redirectUrl | URL to redirect the user after verification |

Example Response:

```json
{
    "sessionId": "5d3b5f0c-2cc9-419d-900a-2bbcd2297e3e",
    "token": "f904c917716c65fa34610c2ca6f02ffdc81db231f72494457a0c61ca8bb628fd",
    "verificationUrl": "https://kyc.apprain.ca/verify/{token}"
}
```

---

## Step 2: Redirect the User

Redirect the user to:

```
verificationUrl
```

The user will complete:

1. Front document upload
2. Back document upload
3. Selfie capture
4. Submission

---

## Step 3: Receive Callback

Once verification is complete, the browser redirects the user to:

```
redirectUrl
```

---

## Step 4: Retrieve Verification Summary

```bash
curl --location --request GET \
'https://kyc.apprain.ca/api/v1/kyc/sessions/{token}/summary' \
--header 'x-client-id: app_43bfa1bacf4435bfc2405459' \
--header 'x-client-secret: secret_75f1d4deec9274c35c65a8744146d5406e19d167e8d3f'
```

The response contains:

- Session status
- Face match result
- OCR extraction results
- Uploaded document details
- External user identifier