# SEED FAQs

<!-- tabs:start -->

#### **General FAQ**

<details><summary>What is TechPass and why do I need it?</summary>

  TechPass is an Identity & Access Management (IAM) and Single Sign-On (SSO) solution. It provides a seamless login experience while accessing tools across Singapore Government Technology Stack (SGTS) and allows to easily manage access control for the users from a centralised location. It is a prerequisite for onboarding your device(non-GSIB) to SEED. For more information, refer to [TechPass Documentation][techpass-documentation].

</details>
<hr />


<details><summary>What is SEED and why should I onboard my device to SEED?</summary>

Security Suite for Engineering Endpoint Devices (SEED) is a Mobile Device Management (MDM) solution. SEED ensures data security to protect the digital information of your organisation from unauthorised access, malicious users, and corruption. When you onboard a non-GSIB device to SEED, it becomes a GMD. It allows you to remotely manage access to highly sensitive data, provide user authentication, and can wipe off data from the device remotely if it is lost or compromised.

</details>
<hr />
<details><summary>I have lost my GMD. What should I do?</summary>

1. Inform the manager-in-charge and operations manager and get an approval to delete the data from the lost device.
2. Raise a [service request][service-request] to notify the SEED team about the lost device.
3. In this service request, indicate if the device had any sensitive data to prioritise the remote wipe.
4. Attach the approvals from your managers so that the SEED Administrator can take the required actions accordingly to prevent any data breach.

</details>
<hr />
<details><summary>What happens when the security of a GMD is compromised?</summary>

Once the SEED team detects that a security of the device is compromised, it will contact the device owner to disconnect the affected device from the network. SEED proceeds to do a remote wipe, after getting the required consent and approval from the device owner and the manager-in-charge, respectively.

</details>
<hr />
<details><summary>What happens when a remote wipe is performed on a GMD?</summary>

Remote wipe in SEED is the feature where SEED administrator can remotely delete and destroy data on a device or system. When remote wipe is performed on a device, all the data on it will be erased. For more information, refer to the [Terms and Policies][terms-and-policies].

</details>
<hr />
<details><summary>Is remote wipe done only on devices that belong to public sector agencies?</summary>

No, remote wipe will be done on any GMD device that is lost to prevent data breach. For more information, refer to the [Terms and Policies][terms-and-policies].

</details>
<hr />
<details><summary>I have already enrolled my device with Microsoft Intune under my organisation or with other MDM solution. Will this impact when I onboard my device to SEED?</summary>

Yes, this impacts your SEED onboarding. Before onboarding to SEED, remove your existing Microsoft Intune enrolment under your organisation's tenancy or other MDM solution on your device.

</details>
<hr />
<details><summary>What data is collected by Microsoft Intune?</summary>

To know about the data collected by Microsoft Intune, refer to [https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect](https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect)

</details>
<hr />

[techpass-documentation]: https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/
[terms-and-policies]: https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/terms-and-policies
[service-request]: https://form.gov.sg/#!/6099efa30d6a0a0012dff367


#### **Onboarding issues for macOS device**

<details>
  <summary>1. What should I do if profile installation fails while installing the management profile?</summary>

<!--<kbd>![profile-installation-failed](images/onboarding-for-macos/profile-installation-failed.png)</kbd>-->

1. Ensure you received an email from us confirming the licence required for SEED onboarding has been assigned to you. If yes, proceed to step 2.
2. Go to the **Apple** menu > **System Preferences** > **Profiles**.
3. If **Management Profile** is already an existing profile, select it and remove it by clicking the minus icon at the lower-left corner.
4. If you are unable to remove Management Profile, uninstall **Company Portal**.
5. Reinstall [Company Portal](https://go.microsoft.com/fwlink/?linkid=853070).
6. Retry onboarding your device to SEED from [**step a. Set up Microsoft Intune to get the required applications and device configuration**](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-onboarding-instructions-for-macos).


</details>
<hr/>


<details>
  <summary>2. While enabling FDA, I can't find TaniumClient. What should I do?</summary>

  1. Open the **Terminal** application and run the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the left pane, choose **Full Disk Access**.
  5. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
  6. Click the plus icon on the **Full Disk Access** pane.
  7. Go to **Macintosh HD** > **Library** > **TaniumClient** and select the application file **TaniumClient**.
  8. Ensure the checkbox beside **TaniumClient** is selected.

</details>
<hr/>

<details>
<summary>3. While enabling FDA, I can't find Microsoft Intune Agent and Microsoft Defender for Endpoint. What should I do?</summary>

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. From the left pane, choose **Full Disk Access**.
4. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
5. Click the plus icon on the Full Disk Access pane and do the following as required:
  - To add **Microsoft Intune Agent**, go to **Macintosh HD** >  **Library** > **Intune** and open **Microsoft Intune Agent.app**.
  - To add **Microsoft Defender for Endpoint**, go to **Application** > select **Microsoft Defender for Endpoint** and click **Open**.
</details>
<hr/>

<details><summary>4. While enabling FDA, I can't find Microsoft Defenders Endpoint Security Extension. Can I proceed with my onboarding?</summary>

Yes, you may proceed with your SEED onboarding and the Microsoft Defenders Endpoint Security Extension should be available within four hours time. If it is still not available after four hours, please raise a [Support Request][raise-support-request] as it is required to ensure the completeness of your onboarding.

</details>
<hr/>

<details><summary>5. While enabling FileVault or FDA, I am unable to unlock Security & Privacy preferences using my current password.</summary>

When your device is enrolled with Microsoft Endpoint Management's Intune, a new password policy comes into effect and this requires you to reset password.  If you enable FileVault or FDA only while onboarding to SEED, reset your password before **step c. Encrypt your hard disk to protect your data at rest** as mentioned on the [SEED onboarding guide for macOS users][seed-onboarding-guide-macos].

*To reset password while enabling FileVault or FDA* :
1. Go to the **Apple** menu > **Lock Screen** or use keyboard shortcut **Command+Control+Q** .
2. Enter your password and press **return**. You will be prompted to reset password.
3. Reset your password and make sure it meets the following requirements:
  - Contain at least 12 characters
  - Not have two consecutive or three sequential characters
  - Contain at least one number and one alphabetic character
  - Not be the same as the previous three passwords

</details>
<hr />

<details><summary>6. After resetting my macOS password, I am unable to log in using the new password, why?</summary>

This may occur if your new password does not meet the following password requirements:

<li>have at least 12 characters</li>
<li>should not have two consecutive or three sequential characters</li>
<li>have at least one number and one alphabetic character</li>
<li>should not be the same as the previous three passwords.</li>
</ul>

<p>There are three password reset options and you may choose one of them to reset password.</p>

<details><summary>Reset password using your Apple ID</summary>
 <p>Refer to <a href="https://support.apple.com/en-gb/guide/mac-help/mh35902/mac">Reset your Mac login password uisng Apple ID</a> for step-by-step instructions.</p></details>

  <details><summary>Reset password using a recovery key</summary>

  *To reset password using recovery key* :
  1. Click the question mark next to the password field in the login window.

  ?> If you don't see a question mark, press and hold the power button until your Mac shuts down, then press the power button to restart your Mac. Alternatively, enter any password three times.

  2. Click  **If you forgot your password, you can reset it using your Recovery Key**.
  3. Enter the recovery key. Make sure to use uppercase letters and to enter the hyphens.
  4. Reset your password.

  </details>

  <details><summary>Reset password using recovery mode</summary>
  <p>If you have do not have an Apple ID or a recovery key, start your Mac in recovery mode.</p>

  *Restart Mac in recovery mode to reset password* :
  1. If your macOS device has M1 chip, turn off the device by pressing the power button and if your macOS device has Intel chip, turn off the device by pressing the power button while holding down `Command + R` keys.

  ?> Release the keys when you see the load bar.

  2. Go to **Applications** > **Utilities** > **Terminal**.
  3. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
  4. Select **My password doesn’t work when logging in** and click **Next**.
  5. If prompted, select the user account for which you need to change password.
  6. Type the old password and new password in the respective fields.
  7. Type the new password in **Verify password** and specify a **Password hint**.
  8. Click **Next**.

  ?> If you are still unable to reset your password, boot into Recovery Mode again repeat steps 2-4 and disable FileVault on the volume “Macintosh HD.

  9. Restart your device and in the login screen, choose your user account and type your new password.

  </details>

  [seed-onboarding-guide-macos]: https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-onboarding-instructions-for-macos


#### **Issues while enrolling in Microsoft Intune**

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

- [Verify if Microsoft Defender is configured correctly on your device][verify-defender-configuration].

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


<!-- tabs:end -->
