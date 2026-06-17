# Apprain KYC

A hosted identity verification platform that enables third-party applications to perform Know Your Customer (KYC) verification through a simple API integration.

## Features

* Hosted KYC verification flow
* Secure session-based verification
* Front document capture
* Back document capture
* Selfie capture
* OCR extraction from identity documents
* Face matching between selfie and identity document
* Verification summary retrieval
* Mobile-friendly hosted experience
* Sandbox environment for testing

---

## Sandbox Access

The sandbox environment is available for integration testing and evaluation purposes.

Sandbox credentials are provided upon request.

For sandbox access, please contact:

```text
reza@apprain.com
reazulk@gmail.com
+1 647 220 3848
```

> Do not upload real customer information or identity documents to the sandbox environment.

---

## Integration Flow

```text
Client Application
        ↓
Create KYC Session
        ↓
Receive verificationUrl
        ↓
Redirect User to Hosted KYC
        ↓
User Completes Verification
        ↓
Redirect to Callback URL
        ↓
Retrieve Verification Summary
        ↓
Receive Verification Result
```

---

## Quick Example

### Create KYC Session

```bash
curl --location 'https://kyc.apprain.ca/api/v1/kyc/sessions' \
--header 'Content-Type: application/json' \
--header 'x-client-id: YOUR_CLIENT_ID' \
--header 'x-client-secret: YOUR_CLIENT_SECRET' \
--data '{
  "externalUserId": "USER-1001",
  "redirectUrl": "https://yourdomain.com/kyc/callback"
}'
```

### Retrieve Verification Summary

```bash
curl --location --request GET \
'https://kyc.apprain.ca/api/v1/kyc/sessions/{token}/summary' \
--header 'x-client-id: YOUR_CLIENT_ID' \
--header 'x-client-secret: YOUR_CLIENT_SECRET'
```

---

## Documentation

* [Quick Start](docs/quick-start.md)
* [API Reference](docs/api-reference.md)
* [Callback & Verification Summary](docs/callback-summary.md)
* [Code Samples](docs/code-samples.md)
* [Mobile Integration](docs/mobile-integration.md)
* [Security Guide](docs/security.md)

---

## Live Demo

### Customer Onboarding System (COS)

Experience the complete onboarding journey using our demonstration environment:

**Customer Journey**

```text
http://cos.apprain.ca
```

This demo showcases:

* Customer onboarding
* OTP verification
* KYC initiation
* Hosted identity verification
* Profile completion workflow

Administrative demonstration access is available upon request.

---

## Mobile Applications

Apprain KYC supports integration with:

* Android applications
* iOS applications
* Hybrid mobile applications

Mobile applications should communicate with their backend services, which in turn communicate with Apprain KYC APIs.

For implementation guidance, refer to:

```text
docs/mobile-integration.md
```

---

## Licensing

Copyright © 2026 Apprain Technologies.

All rights reserved.

---

## Support

For sandbox access, production onboarding, licensing, partnership opportunities, or technical assistance:

```text
Email: reza@apprain.com
Alternate Email: reazulk@gmail.com
Phone: +1 647 220 3848
```

---

## Version

Current Version: **v1.0.0**
