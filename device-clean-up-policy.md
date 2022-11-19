# MDM certificate and device clean-up policy

This article gives an overview of the MDM certificate and the device clean-up policy for SEED users.

## MDM certificate

When users onboard their internet device to SEED, an MDM certificate is assigned to it, and this is valid for a year from the date of onboarding the device to SEED. This certificate gets automatically renewed if you are logged in to your GMD at the time of certificate expiration.

>**Note**:
>- For a successful login to your GMD, your TechPass account must be in an active state.
>- To know how to re-enable a disabled TechPass account, see [TechPass Account Management FAQ](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/support/account).

If your MDM certificate expires and if you log in to your device within 180 days from the MDM certificate expiry date, it will be automatically renewed. In this case, you don't need to re-onboard your device to SEED.

If it is past 180 days of expiry, you will not be able to access the SGTS resources using it. To access the SGTS resources via this device:

1. [Offboard the device from SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/offboard-device/offboard-device-from-seed)
2. [Request for SEED provisioning](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/prerequisites-for-onboarding)
3. [Onboard the device to SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/onboard-device-to-seed).


## Device clean-up policy

The device clean-up policy is applies only to SEED users whose TechPass ID belongs to the TechPass AD. If your TechPass ID's domain is *techpass.gov.sg*, it belongs to the TechPass AD. For example, *james_lee@techpass.gov.sg* belongs to the TechPass AD.

>**Note**:
>- The device clean-up policy is **not applicable** if your TechPass ID belongs to the **WOG AD**. >- If your TechPass ID belongs to the WOG AD, then your TechPass ID is the same as your organisational email address, which is in the format of *\<your_name\>@\<acronym for your agency\>.gov.sg*. For example, *peter_wilson@tech.gov.sg*.

### Purpose of the policy

The purpose of this policy is to remove inactive device records from the Intune portal.

### What happens if GMD is inactive?

If your TechPass ID belongs to the TechPass AD, and if you have not logged into your GMD(the internet device onboarded to SEED) for 90 consecutive days, the GMD becomes inactive, and its records are soft deleted from the Intune portal.

When your device records are "soft deleted", it does not wipe or retire the device. The device record is temporarily deleted from Intune.

SEED administrators will not be able to view details such as the health status of this device and will no longer able to manage it from the DEEP Dashboard.

### Restore my device records on Intune

You can restore the device records on Intune the next time you log in to your GMD device provided:

-	Your TechPass account is still active.
-	Your MDM certificate is still active, or is within 180 days after its expiry.
