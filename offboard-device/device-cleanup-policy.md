# Device clean-up policy

The Device Record Clean-Up Policy aims to manage and maintain the cleanliness of device records in SEED's backend. This documentation outlines the policy for cleaning up onboarded records, ensuring the removal of stale records, and notifying users of impending actions.

## Onboarded records clean-up policy
To prevent stale records from accumulating indefinitely, the following process is established:

   - After 180 days of inactivity, device records are permanently deleted.
   - Users are notified via email 30 days before record deletion, with subsequent notifications everyday.
   - Users can raise a [service request](https://go.gov.sg/seed-techpass-support) if they encounter issues that prevent records from being deleted.

## Restore my device records

You can restore your device records by simply logging in to your GMD device the next time, provided that:

- Your TechPass account is still active.
- Your MDM certificate is still valid or within 180 days after its expiry.
- Your device is configured with the required software, including Tanium, Cloudflare, Microsoft Defender, and Intune.

## MDM certificate

When you onboard your Internet Device to SEED, you receive an MDM certificate that is valid for one year from the date of onboarding. The certificate is automatically renewed if you are logged in to your GMD when it expires.

> **Note**: Ensure that your TechPass account remains active.

If the MDM certificate expires, it can be automatically renewed by logging in to your device within 180 days from the expiration date. In such cases, re-onboarding your device to SEED is not required.

If the certificate remains expired for over 180 days, your device record is permanently deleted, preventing access to SGTS products.