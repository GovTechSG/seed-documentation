# Common issues while enrolling in Microsoft Intune

  <details>
  <summary>1. While onboarding to Microsoft Intune, I get an error message, "Could not download the identity profile from the Encrypted Profile Service. The credentials within the Device Enrolment profile may have expired."</summary>

  One of the possible reasons could be that your device was earlier onboarded to Microsoft Intune by a different user and was not offboarded properly during the pre-onboarding steps.  

  To confirm if that is the case, raise a [Support Request][raise-support-request] with your device serial number.

  The SEED team can verify if your device was previously enrolled to Microsoft Intune under a different user. If this is confirmed, choose on the following to offboard it from Microsoft Intune and then retry onboarding your device to SEED.

  - If you are a Windows user, refer to [SEED offboarding guide for Windows users][seed-offboarding-steps-for-windows].

  - If you are a macOS user, go to **System Preferences**  and locate the old Management Profile. Refer to [SEED offboarding guide for macOS users][seed-offboarding-steps-for-macos].

  </details>
  <hr />

  <details>
    <summary>2. What is the minimum version of macOS needed for onboarding it into Microsoft Intune?</summary>

  Big Sur 11 is the minimum version needed for a successful onboarding. If your macOS is an earlier version, ensure to [upgrade it to a later macOS version](https://support.apple.com/downloads/macos).

  </details>
  <hr />

  <details>
    <summary>3. Why am I prompted to turn on File Vault encryption?</summary>

  File Vault encryption is needed to ensure device security and compliance.

  </details>
  <hr />

  <details><summary>4. Why does my device slowdown after onboarding to Microsoft Intune?</summary>

  SEED is designed to use **Microsoft Defender for Endpoint** to ensure device is free from malware, prevent and respond to advanced threats. If there is any other antivirus or anti-malware running simultaneously, it could compromise the performance of the operating system. To resolve this, disable or uninstall antivirus other than **Microsoft Defender for Endpoint**.

  </details>
  <hr />

  <details><summary>5. While enrolling my device to SEED, I get an error message, "<em>Couldn’t add your device. Wait a few minutes, then try again or contact your company support.</em>" What should I do?
  </summary>

  As suggested wait for few minutes, retry enrolling your device to Microsoft Intune and click **Approve** in the management profile.

  </details>
  <hr />

  <details>
  <summary>6. While approving the management profiles, I get a message "<em>Profiles cannot be approved while using remote or automated input method.</em>” What should I do?</summary>

   Upgrade to the [latest macOS version][upgrade-macos] and ensure there is enough disk space available on your Mac device before retrying.

  </details>
  <hr />

<details><summary>7. Why am I prompted to turn on my system integrity protection on my macOS device?</summary>

  This is a policy requirement of the SEED team. System Integrity Protection is a security technology in OS X El Capitan and later that's designed to help prevent potentially malicious software from modifying protected files and folders on your macOS. System Integrity Protection restricts the root user account and limits the actions that the root user can perform on protected parts of the macOS.

 </details><hr />

<details><summary>8. What should I do when I get an error message, “<em>You can’t use this version of the application Company Portal with this version of OS X.</em>" </summary>

 Upgrade to the [latest macOS version][upgrade-macos].

 </details>
 <hr />

<details>
<summary>9. Tanium client returns a 400 Bad Request Error when contacted by the Cloudflare Access landing page via localhost. What should I do now? </summary>

This is due to the time synchronisation issue between Cloudflare and Tanium client. To fix this, resync the local time of your macOS or Windows machine.

To check and synchronise your device time with the internet time server:

  <details><summary>For macOS device</summary>

   1. From the **Apple** menu, go to **System Preferences** > **Date & Time**.
   2. Click the lock icon and use your Touch ID or enter your password to unlock.
   3. Select the **Set date and time automatically** checkbox.
   4. To use a custom network time server, enter the domain name of the server in the .
   ![synchronise your Mac time](../images/sync-clock-on-mac.png)
  </details>

  <details><summary>For Windows 10 device</summary>

    1. Open the **Start** menu and click **Settings**.
    1. Choose **Time & Language**.
    1. Turn on **Set time automatically**.
    1. Click **Sync now** to synchronise with the time server.
    1. If you’d like to use a custom network time server, click **Date, time & regional formatting** from **Related Settings** at the upper-right corner. The **Region** settings page is displayed.
    1. Click **Additional date, time & regional settings** from **Related settings** at the upper-right corner. The **Clock and Region settings** page is displayed.
    1. Click **Date and Time**.
    1. Go to the **Internet Time** tab and select **Change settings**.
    1. Enter the domain name of the server.

  </details>
  </details>  
  <hr />

<details>
<summary>10. After onboarding to SEED, I did not receive the successfully onboarded email. What should I do?</summary>

Possible reasons could be:

- Defender or any other antivirus solution previously installed on the device was not completely removed before onboarding to SEED.
- Tanium and Cloudflare did not get installed while onboarding to SEED.

Before raising a support request, confirm the following:

- [Verify if Microsoft Defender is configured correctly on your device](../verify-microsoft-defender-is-configured-correctly-for-your-os.md).

- Check if Tanium and Cloudflare are installed. These applications will be automatically installed while enrolling your device to SEED. If they are not installed, raise a [Support Request][raise-support-request].

</details>
<hr />

<details>
<summary>11. What should I do if my device does not get renamed automatically after onboarding to SEED?</summary>

This can happen if Defender or any other antivirus already installed on the device was not completely removed before onboarding to SEED. To confirm this, [verify if Microsoft Defender is configured correctly on your device][verify-defender-configuration].

</details>
<hr />

<details>
<summary>12. Microsoft Defender was not automatically installed after enrolling to Company Portal?</summary>

This can happen if Defender or any other antivirus solution previously installed on the device was not completely removed before onboarding to SEED.

To confirm this, [verify if Microsoft Defender is configured correctly for your OS][verify-defender-configuration].

</details>
<hr />

<details>
<summary>13. I am unable to connect to AWS VPN client on port 443? </summary>

This is a known issue with Microsoft Defender version 101.54.16. To resolve this, install Microsoft Defender version 101.56.35 or later.

</details>
<hr />


[seed-offboarding-steps-for-windows]: ../seed-offboarding-instructions-for-windows.md
[seed-offboarding-steps-for-macos]: ../seed-offboarding-instructions-for-macos.md
[verify-defender-configuration]: ../verify-microsoft-defender-is-configured-correctly-for-your-os.md
[upgrade-macos]: https://support.apple.com/downloads/macos
[raise-support-request]: ../raise-an-incident-support-request.md
