# Announcements

| Date  | Announcement |
| ------------- |:-------------:|
| July 12, 2022| Password policy for Windows will be implemented for your GMD on 19th July 2022, 12:00 SGT. <br>Password complexity requirements will be set for both Windows password and Windows Hello PIN as mentioned below: <br><br>**Password or PIN type**: Alphanumeric<br>**Password or PIN Complexity**: Require digits(0 through 9), lowercase and uppercase letters<br>**Minimum password or PIN length**: 12<br>**Password expiration**: 365 days<br>**Number of previous passwords to prevent reuse**: 3<br><br>**Customer Impact:**<br>After this new password policy is implemented, when Windows users log into their device, their device will prompt them to change their password and PIN if their current settings do not meet the specified password requirements.<br><br>**Action Required:**<br>Ensure that you have backed-up your BitLocker keys in another device to avoid losing your data. For more information on how to back-up the BitLocker keys, please refer to the **Windows** tab in [Encrypt your hard disk drive to protect your data at rest](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/prerequisites-for-onboarding?id=encrypt-your-hard-disk-drive-to-protect-your-data-at-rest).<br><br>**Additional Information**:<br>If you have any issues, please [raise an incident support request](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/raise-an-incident-support-request) with the respective SGTS service or products team. |
| June 29, 2022      | Newer version of Cloudflare WARP Client will be installed on your GMD on July 01, 2022 18:00 SGT:<br> - version 2022.5.342 for macOS<br> - version 2022.5.341 for Windows<br><br> The newer version of the Cloudflare WARP client will fix the memory leak issue observed on the older Cloudflare WARP clients. <br><br> **Customer Impact:**<br> During the client installation, your GMD will be disconnected from the SGTS resources you are accessing at that time. This installation may take up to five minutes.<br> Users whose GMD already has the newer version of the Cloudflare WARP client will not be impacted, and hence no action is required by them.<br><br>**Action Required:**<br> Ensure your GMD is connected to an active internet connection during the installation.<br><br>**Additional Information:**<br>- If you can't access SGTS services after the newer client version is installed, please reboot your GMD.<br>- If the issue persists, please [raise an incident support request](raise-an-incident-support-request) with the respective SGTS service or products team.|
|June 21, 2022 |An issue has been identified with Cloudflare services on June 21 14:34 SGT. A fix has been implemented on Jun 21, 15:20 SGT and we are monitoring the outcome.<br><br>**Customer Impact:**<br> Users may have observed 500 errors while accessing the Internet and Cloudflare protected SGTS services using Cloudflare WARP.<br>While we monitor the fix, if you are still unable to access the Internet, please turn off WARP to access the Internet and raise an [incident support request](raise-an-incident-support-request) with the respective SGTS service or product team.<br>You may also visit the [Cloudflare status page](https://www.Cloudflarestatus.com/) for recent updates on this issue. |





<!--### June 29, 2022

Newer version of Cloudflare WARP Client will be installed on your GMD on July 01, 2022 18:00 SGT:
- version 2022.5.342 for macOS
- version 2022.5.341 for Windows

The newer version of the Cloudflare WARP client will fix the memory leak issue observed on the older Cloudflare WARP clients.

**Customer Impact:**

During the client installation, your GMD will be disconnected from the SGTS resources you are accessing at that time. This installation may take up to five minutes.

Users whose GMD already has the newer version of the Cloudflare WARP client will not be impacted, and hence no action is required by them.

**Action Required:**

Ensure your GMD is connected to an active internet connection during the installation.

**Additional Information:**

If you can't access SGTS services after the newer client version is installed, please reboot your GMD. If the issue persists, please [raise an incident support request](raise-an-incident-support-request) with the respective SGTS service or products team.


### June 21, 2022

An issue has been identified with Cloudflare services on June 21 14:34 SGT. A fix has been implemented on Jun 21, 15:20 SGT and we are monitoring the outcome.

**Customer Impact:**

Users may have observed 500 errors while accessing the Internet and Cloudflare protected SGTS services using Cloudflare WARP.

While we monitor the fix, if you are still unable to access the Internet, please turn off WARP to access the Internet and raise an [incident support request](raise-an-incident-support-request) with the respective SGTS service or product team.

You may also visit the [Cloudflare status page](https://www.Cloudflarestatus.com/) for recent updates on this issue.-->
