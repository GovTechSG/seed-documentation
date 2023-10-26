# Onboarding FAQ

<details>
  <summary>How can I confirm the successful onboarding of my Internet Device to SEED?</summary>

After completing the onboarding process for your device to SEED, you should expect to receive a confirmation email indicating successful onboarding within two hours. This email will be sent to your organizational email address.

If you have not received the confirmation email after this two-hour period, [raise a service request](https://go.gov.sg/seed-techpass-support) for assistance.
</details>

<details>
  <summary>What should I do if profile installation fails during management profile installation?</summary>

1. Ensure you have received an email confirming that the required SEED onboarding license has been assigned to you. If you have received this confirmation, proceed to step 2.
2. Navigate to the **Apple** menu > **System Preferences** > **Profiles**.
3. If you already have an existing **Management Profile**, select it and remove it by clicking the minus icon at the lower-left corner.
4. If you encounter difficulties removing the **Management Profile**, uninstall **Company Portal**.
5. Reinstall [Company Portal](https://go.microsoft.com/fwlink/?linkid=853070).
6. [Onboard your device to SEED](onboard-device/identify-onboarding-persona).

</details>
<details>
  <summary>How does enrolling my device with Microsoft Intune or other MDM solutions impact my SEED onboarding?</summary>

  Enrolling your device with Microsoft Intune or other MDM solutions can have an impact on your SEED onboarding process. It's important to remove any existing enrollments with Microsoft Intune or other MDM solutions from your device before proceeding with SEED onboarding.

</details>
<details>
  <summary>What data is collected by Microsoft Intune?</summary>

  To learn about the data collected by Microsoft Intune, please refer to [Data collection in Intune](https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect).

</details>
<details>
  <summary>Why is Microsoft Defender not automatically installed after enrolling in Company Portal?</summary>

  This can happen if Defender or any other antivirus solution previously installed on the device was not completely removed before onboarding to SEED. Please verify that Microsoft Defender is correctly configured on your device.

  For detailed steps on verifying Microsoft Defender on your device, please refer to the appropriate guide:
    - [macOS 14 and 13](/post-onboarding-instructions/macos-latest.md)
    - [macOS 12](/post-onboarding-instructions/macos.md)
    - [Windows](/post-onboarding-instructions/windows.md)

</details>
  
<details>
  <summary>While onboarding to Microsoft Intune, I receive an error message: "Could not download the identity profile from the Encrypted Profile Service. The credentials within the Device Enrolment profile may have expired." What should I do?</summary>

  One possible reason for this error is that your device may have been previously onboarded to Microsoft Intune by a different user and was not properly offboarded during the pre-onboarding steps.

  To confirm this, please [raise a service request](https://go.gov.sg/seed-techpass-support) and provide your device's serial number. The SEED team will investigate whether your device was previously enrolled in Microsoft Intune under a different user.

  If this is confirmed, you can choose one of the following options to offboard your device from Microsoft Intune and then retry the SEED onboarding process:

  - For Windows users, refer to the [SEED offboarding steps for Windows](/offboard-device/windows-offboarding-guide.md).
  - For macOS users, go to **System Preferences** and locate the old Management Profile. Follow the [SEED offboarding steps for macOS](/offboard-device/macos-offboarding-guide.md).
</details>
  
<details>
  <summary>What should I do if my device is not automatically renamed after SEED onboarding?</summary>

  This can happen if Defender or any other antivirus already installed on the device was not completely removed before onboarding to SEED. To confirm this, verify if Microsoft Defender is configured correctly on your device.

</details>


<details>
  <summary>While enabling Full Disk Access (FDA), I could not find <b>TaniumClient</b>. What should I do?</summary>

  If **TaniumClient** is not visible while enabling Full Disk Access (FDA), follow these steps:


  1. Open the **Terminal** application and run the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the left pane, choose **Full Disk Access**.
  5. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
  6. Click the plus icon on the **Full Disk Access** pane.
  7. Go to **Macintosh HD** > **Library** > **TaniumClient** and select the application file **TaniumClient**.
  8. Ensure the checkbox beside **TaniumClient** is selected.

</details>

<details>
  <summary>While enabling Full Disk Access (FDA), I cannot find <b>Microsoft Intune Agent</b> and <b>Microsoft Defender for Endpoint</b>. What should I do?</summary>

  If **Microsoft Intune Agent** and **Microsoft Defender for Endpoint** are not visible while enabling Full Disk Access (FDA), follow these steps:

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. In the left pane, select **Full Disk Access**.
4. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
5. Click the plus icon on the **Full Disk Access** pane and follow these steps as needed:
   - To add "Microsoft Intune Agent," navigate to **Macintosh HD** > **Library** > **Intune** and open **Microsoft Intune Agent.app**.
   - To add "Microsoft Defender for Endpoint," go to **Applications**, select **Microsoft Defender for Endpoint**, and click **Open**.

</details>

<details>
  <summary>While enabling Full Disk Access (FDA), I cannot find <b>Microsoft Defender Endpoint Security Extension</b>. Can I proceed with onboarding?</summary>

  Yes, you can proceed with your SEED onboarding, and **Microsoft Defender Endpoint Security Extension** should become available within four hours. If it does not become available after four hours, please [raise a service request](https://go.gov.sg/seed-techpass-support) as it is necessary to ensure the completeness of your onboarding.

</details> 

<details>
  <summary>When enabling FileVault or FDA, I am unable to unlock Security & Privacy preferences using my current password. What should I do?</summary>

  This issue may arise due to a new password policy that requires you to reset your password. 
  
  Follow these steps:

1. Go to the **Apple** menu and choose **Lock Screen** or press **Command+Control+Q**.
2. Enter your current password and press **Return**.
3. You will be prompted to reset your password.
</details>

<details>
<summary>I did not receive the successfully onboarded email after onboarding to SEED. What should I do?</summary>

Possible reasons:

- Microsoft Defender or any other antivirus solution previously installed on the device was not completely removed before onboarding to SEED.
- Tanium and Cloudflare were not installed while onboarding to SEED.

Before raising a service request, confirm the following:

- Verify if Microsoft Defender is configured correctly on your device.

- Check if Tanium and Cloudflare are installed. These applications should be automatically installed during device enrolment with SEED. If they are not installed, [raise a service request](https://go.gov.sg/seed-techpass-support).

</details>


<details>
  <summary>While approving the management profiles, I get a message <b>Profiles cannot be approved while using remote or automated input method</b>. What should I do?</summary>

  To resolve this issue, upgrade to the [latest macOS version][upgrade-macos] and ensure your Mac device has sufficient available disk space before attempting to approve the management profiles.


</details>

<details>
  <summary>How can I reset my password on macOS?</summary>
If you encounter password reset issues on macOS, it may be due to new password requirements. Before you proceed to reset your macOS password, please ensure that the new password meets the following requirements:

- It should contain at least 12 characters.
- It should not be the same as the previous three passwords.
- The same character cannot be used consecutively.
- It cannot have three sequential characters.
- It should contain at least one number and one alphabetic character.

Now, here are three options for resetting your macOS password:

<details>
  <summary>Reset password using Apple ID</summary>

Refer to [Reset your macOS login password using Apple ID](https://support.apple.com/en-gb/guide/mac-help/mh35902/mac) for step-by-step instructions.
</details>

<details>
  <summary>Reset password Using recovery key</summary>

**To reset your password using a recovery key**:

1. Click the question mark next to the password field in the login window.

?> If you do not see a question mark, press and hold the power button until your Mac shuts down, then press the power button to restart your Mac. Alternatively, enter any password three times.

2. Click **If you forgot your password, you can reset it using your Recovery Key**.
3. Enter the recovery key, making sure to use uppercase letters and include hyphens.
4. Reset your password.
</details>

<details>
  <summary>Reset password using recovery mode</summary>

If you do not have an Apple ID or a recovery key, you can reset your password in recovery mode based on your Mac's chip:

<!-- tabs:start -->

#### **M1 Chip**
1. Restart or shut down your device by pressing the power button until the screen is black and all lights, including the Touch Bar, are off.
2. Press and hold the power button on your Mac until the **Loading startup options** screen appears. After a few seconds, you’ll see two icons: **Macintosh HD** and **Options**.
3. Click **Options** and select your user account, then click **Next**.
4. Enter your password to continue.
5. Go to **Applications** > **Utilities** > **Terminal**.
6. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
7. Choose **My password doesn’t work when logging in** and click **Next**.
8. If prompted, select the user account for which you need to change the password.
9. Enter the old password and your new password in the respective fields.
10. Type the new password again to verify and provide a password hint.
11. Click **Next**.
12. Restart your device and, on the login screen, select your user account and enter the new password.

> **Note**:

> 1. If you still cannot reset your password, repeat steps 1-6.
> 2. Select **My keyboard isn't working when typing my password to log in** and click **Next**.
> 3. Disable FileVault on the **Macintosh HD** volume.
> 4. Restart your device. On the login screen, select your user account and enter the new password.

#### **Intel chip**

1. Restart your device by pressing the power button while holding down the `Command + R` keys.
2. Release the keys when you see the load bar.
3. Go to **Applications** > **Utilities** > **Terminal**.
4. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
5. Choose **My password does not work when logging in** and click **Next**.
6. If prompted, select the user account for which you need to change the password.
7. Enter the old password and your new password in the respective fields.
8. Type the new password again to verify and provide a password hint.
9. Click **Next**.
10. Restart your device. On the login screen, select your user account and enter the new password.

> **Note**:

> 1. If you still cannot reset your password, repeat steps 1-4.
> 2. Select **My keyboard is not working when typing my password to log in** and click **Next**.
> 3. Disable FileVault on the **Macintosh HD** volume.
> 4. Restart your device and, on the login screen, select your user account and enter the new password.

<!-- tabs:end -->

</details>
</details>
</details>     

<details>
  <summary>What should I do if my onboarding fails while registering my Intune Device ID on the TechPass portal?</summary>

As a prerequisite, ensure the device you are onboarding to SEED has a stable internet connectivity until you see the **Onboarded** Status on the TechPass portal.

![intune-device-id-errors-tp-portal](../images/intune-device-id-error-faq.png)

| Reason for failed onboarding | Action required |
| ---|---|
| Unexpected Error| [Raise a service request](https://go.gov.sg/seed-techpass-support). |
| Software Misconfiguration Error | [Raise a service request](https://go.gov.sg/seed-techpass-support).|
| Endpoint Error | <br>1. Ensure the device you are onboarding to SEED has a stable internet connectivity until you see the **Onboarded** Status on the TechPass portal.<br>2. Go to the [TechPass portal](https://portal.techpass.gov.sg/).<br>3. At the top right, go to your user name and click **My Account**. Your profile details are displayed.<br>4. Go to the **SEED Devices** section and click **Retry**. <br>5. If the error persists, [Raise a service request](https://go.gov.sg/seed-techpass-support). |
| Software Installation Error | 1. Restart the device you are onboarding to SEED.<br>2. After 10-15 minutes, go to the [TechPass portal](https://portal.techpass.gov.sg/).<br>3. At the top right, go to your user name and click **My Account**. Your profile details are displayed.<br>4. Go to the **SEED Devices** section and click **Retry**. <br>5. If the error persists, [Raise a service request](https://go.gov.sg/seed-techpass-support).|
| Internal Error | 1. Restart the device you are onboarding to SEED.<br>2. After 10-15 minutes, go to the [TechPass portal](https://portal.techpass.gov.sg/).<br>3. At the top right, go to your user name and click **My Account**. Your profile details are displayed.<br>4. Go to the **SEED Devices** section and click **Retry**. <br>5. If the error persists, [Raise a service request](https://go.gov.sg/seed-techpass-support).|
| Device that is trying to onboard is a DWP device. Please onboard with a non-DWP device.| You cannot onboard a DWP device to SEED. You can onboard only an Internet Device to SEED. |

</details>


   




[verify-defender-configuration]: post-onboarding-instructions/verify-microsoft-defender-is-configured-correctly-for-your-os
[raise-support-request]: https://go.gov.sg/seed-techpass-support
[upgrade-macos]: https://support.apple.com/downloads/macos