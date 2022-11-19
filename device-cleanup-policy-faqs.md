# Device cleanup policy FAQs

<details>
<summary style="font-size:20px;font-weight:bold">What should I do if I am unable to browse the internet using Cloudflare WARP?</summary>

I am regularly using TechPass account on my GSIB device, is my GMD considered to be active?

No, GMD is considered to be active only if you regularly log in to it. Your GMD becomes inactive if you have not logged into it for 90 consecutive days.

What happens if my device become inactive?

If your GMD becomes inactive, its records are "soft deleted" from the Intune portal.

When your device records are "soft deleted", it does not wipe or retire the device. The device record is temporarily deleted from Intune.

How to restore my device records on Intune?

Log in to your GMD device provided:

-	Your TechPass account is still active. Note to re-enable a disabled TechPass account, see [TechPass Account Management FAQ](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/support/account)
-	Your MDM certificate is still active, or is within 180 days after its expiry. For more information, refer to MDM certificate on [MDM certificate and device cleanup policy](device-cleanup-policy).


I am back to work after taking leave for 3 or more months, do I need to re-onboard my device to SEED?

Refer to MDM certificate on [MDM certificate and device cleanup policy](device-cleanup-policy).


Will I receive any notification regarding MDM certificate expiration?

No, you won’t receive any notification for this.

How should I re-onboard to SEED?

1. [Offboard the device from SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/offboard-device/offboard-device-from-seed)
2. [Request for SEED provisioning](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/prerequisites-for-onboarding)
3. [Onboard the device to SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/onboard-device-to-seed).
