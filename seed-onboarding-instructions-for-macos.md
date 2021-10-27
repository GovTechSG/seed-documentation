# Onboarding to SEED using macOS

This sections explains public officers and vendors the prerequisites for onboarding and how to onboard into SEED using macOS.

**Prerequisites** : [Get your macOS ready for onboarding](#seed-pre-onboarding-clean-up-instructions-for-macos).

During this onboarding journey you will do the following:
1. [Get your macOS device managed by Intune Company Portal app](#get-your-macos-device-managed-by-intune-company-portal-app).
2. [Ensure SIP is enabled on your device](#ensure-sip-is-enabled-on-your-device).
3. [Ensure your device hard disk is encrypted](#ensure-your-device-hard-disk-is-encrypted).
4. [Enable Full Disk Access(FDA)](#enable-full-disk-access).
5. [Enrol your macOS on Cloudflare using WARP client](#enrol-your-macos-on-cloudflare-using-warp-client)


<!--?> If you encounter any issues while onboarding, refer to [Common issues and resolution](#common-issues-and-resolution) section in the appendix before reaching out to the SEED team for support.-->


## Get your macOS device managed by Intune Company Portal app
Enrol your macOS device with the Intune Company Portal app to get a secured access to your email, files, and applications.

*To manage your device by Intune Company Portal app* :

1. Download and install [**Company Portal**](https://go.microsoft.com/fwlink/?linkid=853070).

2. Open the **Company Portal** application and click **Sign in**.

<kbd>![sign-in](images/onboarding-for-macos/sign-in.png)</kbd>

3. Choose the appropriate login credentials to sign in with two-factor authentication:
   - If you are a public officer, use your [WOG ID](terms-definitions).
   - If you are a vendor, use your [TechPass ID](terms-definitions).

<kbd>![log-in-to-gcc](images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

?> If you're using the text message method for authentication, after you enter your password, you'll need to enter the verification code sent to your phone. Based on what you [set up](https://account.activedirectory.windowsazure.com/Proofup.aspx), other authentication methods have different ways to perform the 2FA.

4. Once you have signed in, click **Begin**.

<kbd>![](images/onboarding-for-macos/begin.png)</kbd>

5. Review privacy information. Then click **Continue**.

![review-privacy-info](images/onboarding-for-macos/review-privacy-info-blurred.png)

6. On the **Install management profile** page, click **Download profile**.

<kbd>![install-management-profile](images/onboarding-for-macos/install-management-profile.png)</kbd>

7. Follow the on-screen instructions to allow Microsoft Intune to manage your device. The **Profiles** page is displayed.

<kbd>![profile-1](images/onboarding-for-macos/profile-1.png)</kbd>

Tip:
 - If **Profiles** page is not displayed, go to the **Apple** menu > **System Preferences** > **Profiles**.

 - If **Management Profile** is not displayed, then from the left side menu, select **Management Profile**.

 - If Profile installation fails, refer to [Common issues and resolution](#common-issues-and-resolution).

8. Click **Install**.

![profile](images/onboarding-for-macos/profile-2.png)

The configuration profiles that Intune needs to deploy will be installed. You will see a list of profiles as shown below.

![list-of-profiles](images/onboarding-for-macos/list-of-profiles.png)

10. Open the **Company Portal** application again.

<!--![all-set](images/onboarding-for-macos/all-set-1.png)-->

11. You will see the success message. Click **Done**.

![all-set](images/onboarding-for-macos/all-set-2.png)

<!--?> Onboarding is not yet complete. Now you proceed to verify if System Integrity Protection(SIP) is enabled on your device. SIP protects your system from the execution of unauthorised code.-->

## Ensure SIP is enabled on your device
Make sure SIP is enabled to prevent executions of unauthorised codes.

To verify if SIP is enabled, open **Terminal** and run the following command:

  ```
  csrutil status
  ```

 If the response on your **Terminal** is ``System Integrity Protection status: enabled``, it indicates that SIP is already enabled on your device.

 ?>  If it is currently disabled, run the command ``csrutil enable`` on the **Terminal** and restart your device before proceeding with the following steps.

## Ensure your device hard disk is encrypted
To protect the privacy of your files and user data secured, ensure your device hard disk is encrypted.

*To ensure your device hard disk is encrypted* :

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **FileVault** tab.
3. If you see **Turn on FileVault**, go to step 4 or proceed to [Enable Full Disk Access(FDA)](#enable-full-disk-access).
4. Click the lock icon and use your Touch ID or enter your password to unlock.
5. Click **Turn on FileVault**.
6. You will be prompted to specify how you would like to unlock your device if you forget your device password. Select **Create a recovery key and do not use my iCloud account**.

<kbd>![create-recovery-key](images/onboarding-for-macos/create-recovery-key-1.png)</kbd>

 ?>  Save this key on a different device.

<!--Note:

- Some applications that SEED depends on require Full Disk Access (FDA) in order to function.
- As of Catalina, users may be required to give explicit consent for FDA.
-->
## Enable Full Disk Access
Enable Full Disk Access is for TaniumClient, Microsoft Defender ATP and Microsoft Defender ATP Security Extension.
*To enable FDA* :
1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. From the side menu, choose **Full Disk Access**.
4. Click the lock icon at the bottom and use your Touch ID or enter your  password to unlock.
5. Ensure the following applications are listed:
     - Tanium Client
     - Microsoft Intune Agent
     - Microsoft Defender ATP
     - Microsoft Defender ATP Security Extension

 ?>  If **TaniumClient** is missing, refer to [Common issues and resolution](#common-issues-and-resolution) before proceeding further.

6. Select the checkboxes beside these applications.

 <kbd>![fda-enabled](images/onboarding-for-macos/all-apps-fda-enabled.png)</kbd>

## Enrol your macOS on Cloudflare using WARP client

**Prerequisites:**
1. Ensure that you have Cloudflare WARP client installed in your device. If not install it from [Clouhttps://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-macos-1/distribution_groups/release](Clouhttps://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-macos-1/distribution_groups/release)

2. Disconnect from any other VPN that might be running as that could clash with Cloudflare.

*To enrol macOS on Cloudflare using WARP client* :

1. Open the Cloudflare WARP client from the menu bar on the top right corner of your Mac device.

![cloudflare-warp-icon](images/onboarding-for-macos/cloudflare-icon.png)

?>  You can also press ``Command+Spacebar`` and search for  **Cloudflare WARP** application to open it.


You will see the information page, followed by your privacy policy.

2. Click **Next** and then **Accept**.

![accept-privacy-policy](images/cloudflare-warp-macos/accept-privacy-policy.png)

3. When prompted to sign in, select **Azure AD – TechPass Prod**.

![gcc-cloudflare-access-signin](images/cloudflare-warp-macos/gcc-cloudflare-access-signin.png)

?>  If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

4. Choose the appropriate login credentials to sign in with two-factor authentication:
 - If you are a public officer, use your [WOG ID](term-definitions).
 - If you are a vendor, use your [TechPass ID](term-definitions).


 <!--When greeted with the Microsoft sign-in page, sign in using your WOG ID (i.e. [your\_name@tech.gov.sg](mailto:your_name@tech.gov.sg)) if you are a public officer, or your TechPass ID (i.e. [your\_name@techpass.gov.sg](mailto:your_name@techpass.gov.sg)) if you are a vendor.-->

![techpass-sign-in](images/cloudflare-warp-macos/techpass-sign-in.png)

5. Once you have successfully signed in, click the Cloudflare WARP icon.

![cloudflare-warp-icon](images/onboarding-for-macos/cloudflare-icon.png)

The following screen is displayed.

![warp-teams](images/cloudflare-warp-macos/warp-teams.png)

?>  If you need to connect to a different VPN, disconnect and quit from the WARP client.


## Post onboarding notes

<!--- If you encounter any issues during onboarding, refer to [Common issues and resolution](#common-issues-and-resolution) before reaching out to the SEED team.-->
- If onboarding was successful, you will receive an email informing you that your device is successfully onboarded.
  - Public officers receive this email in their *GSIB email inbox* while vendors receive it at their *work email address* which was used to create their TechPass account.
  - Due to the nature of the verification process, it may take up to an hour to receive this email. if you do not receive it after an hour, please  contact the SEED team.
  - Shortly after this email, you will receive a desktop notification prompting to restart the device.
1. Restart your device.
2. If prompted to enter your password, enter your password.

?>  While restarting, you will be notified that your device is renamed and will be prompted to reset your password.

3. Reset your password.

<!--that **your device has been renamed and will restart in 5 minutes**. This is expected, and the rename is required for SEED to function properly. **Please do not change your device name thereafter**.-->

## Common issues and resolution

1. What should I do if profile installation fails while installing the management profile?

<kbd>![profile-installation-failed](images/onboarding-for-macos/profile-installation-failed.png)</kbd>

  1. Go to the **Apple** menu > **System Preferences** > **Profiles**.
  2. If **Management Profile** is already an existing profile, select it and remove by clicking the minus icon at the bottom left corner.

2. While enabling FDA, I can't find **TaniumClient**. What should I do?

  1. Open the **Terminal** application and enter the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the side menu, choose **Full Disk Access**.
  5. Click the lock icon at the bottom and use your Touch ID or enter your password to unlock.
  6. Click the plus icon at the bottom and from **Applications**, select **TaniumClient**.
  7. Select the checkbox beside **TaniumClient**.
