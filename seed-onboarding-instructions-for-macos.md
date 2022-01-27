# SEED onboarding guide for Mac users

This sections explains how public officers and vendors can onboard to SEED using their macOS device. Before onboarding, take a look at the [prerequisites for SEED onboarding](prerequisites-for-onboarding).


?>  Based on your Mac settings, you may be prompted to restart or reset your password while onboarding.
For a smooth onboarding journey, it is important to link your Apple ID to this Mac device. Generate a recovery key and keep it safe in a place other than the Mac device that you are going to onboard to SEED.

During this onboarding journey you will do the following:


<details>
  <summary>a. Set up Intune to get the required applications and device configuration</summary><br>

  1. Download and install [**Company Portal**](https://go.microsoft.com/fwlink/?linkid=853070).

  2. Open the **Company Portal** application and click **Sign in** to log in using your TechPass credentials.

  <kbd>![sign-in](images/onboarding-for-macos/sign-in.png)</kbd>

  3. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. However, if you are a public officer, you must first approve your WOG login before approving your Techpass login.

  <kbd>![log-in-to-gcc](images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

  ?> The above page is displayed only for public officers. Refer to [TechPass documentation](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/) for more information.

  4. Once you have signed in, click **Begin**.

  <kbd>![](images/onboarding-for-macos/begin.png)</kbd>

  5. Review privacy information. Then click **Continue**.

  <kbd>![review-privacy-info](images/onboarding-for-macos/review-privacy-info-blurred.png)</kbd>

  6. On the **Install management profile** page, click **Download profile**.

  <kbd>![install-management-profile](images/onboarding-for-macos/install-management-profile.png)</kbd>

  7. Follow the on-screen instructions to allow Microsoft Intune to manage your device. The **Profiles** page is displayed.

  <kbd>![profile-1](images/onboarding-for-macos/profile-1.png)</kbd>

  Tip:
   - If **Profiles** page is not displayed, go to the **Apple** menu > **System Preferences** > **Profiles**.

   - If **Management Profile** is not displayed, then from the left side menu, select **Management Profile**.

   - If Profile installation fails, refer to [Common issues while onboarding using macOS](common-issues-while-onboarding-using-macos).

  8. Click **Install**.

  <kbd>![profile](images/onboarding-for-macos/profile-2.png)</kbd>

  The configuration profiles that Intune needs to deploy will be installed. You will see a list of profiles as shown below.

  <kbd>![list-of-profiles](images/onboarding-for-macos/list-of-profiles.png)</kbd>

  9. Open the **Company Portal** application again.

  10. You will see the success message. Click **Done**.

  <kbd>![all-set](images/onboarding-for-macos/all-set-2.png)</kbd>


</details>

<details>
  <summary>b. Enable System Integrity Protection (SIP) to prevent unauthorised code executions</summary><br>

  - To verify if SIP is enabled, open **Terminal** and run the command `csrutil status`.


   If the response on your **Terminal** is `System Integrity Protection status: enabled`, it indicates that SIP is already enabled on your Mac.

  Note:  If it is currently disabled, run the command `csrutil enable` on the **Terminal** and restart your device before proceeding further.

</details>
<details>
  <summary>c. Encrypt your hard disk to protect your data at rest</summary><br>

  1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  2. Click the **FileVault** tab.
  3. If you see **Turn on FileVault**, go to step 4 or proceed to **Enable Full Disk Access(FDA)**.
  4. Click the lock icon and use your Touch ID or enter your password to unlock.
  5. Click **Turn on FileVault**.
  6. When prompted to specify how you would like to unlock your device if you forget your device password,  select **Create a recovery key and do not use my iCloud account**.

  <kbd>![create-recovery-key](images/onboarding-for-macos/create-recovery-key-1.png)</kbd>

   ?>  Save this key on a different device.

</details>
<details>
  <summary>d. Enable Full Disk Access(FDA) for the applications installed for SEED</summary><br>

  1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  2. Click the **Privacy** tab.
  3. From the side menu, choose **Full Disk Access**.
  4. Click the lock icon at the bottom and use your Touch ID or enter your  password to unlock.
  5. Ensure the following applications are listed:
       - Tanium Client
       - Microsoft Intune Agent
       - Microsoft Defender ATP
       - Microsoft Defender ATP Security Extension

   ?>  If any of the listed application is missing, please refer to [Common issues while onboarding using macOS](common-issues-while-onboarding-using-macos).

  6. Select the checkboxes beside these applications.

   <kbd>![fda-enabled](images/onboarding-for-macos/all-apps-fda-enabled.png)</kbd>


</details>
<details>
  <summary>e. Enrol on Cloudflare using WARP client to connect to protected engineering resources</summary><br>


  1. Ensure that you have Cloudflare WARP client installed in your device. If not, install the latest [Cloudflare WARP](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-macos-1/distribution_groups/release) version.

  2. Disconnect from any other VPN that might be running as that could clash with Cloudflare.

  3. Open the Cloudflare WARP client from the menu bar on the top right corner of your Mac device.

  <kbd>![cloudflare-warp-icon](images/onboarding-for-macos/cloudflare-icon.png)</kbd>

  ?>  You can also press ``Command+Spacebar`` and search for  **Cloudflare WARP** application to open it.


 You will see the information page, followed by your privacy policy.

  4. Click **Next** and then **Accept**.

  <kbd>![accept-privacy-policy](images/cloudflare-warp-macos/accept-privacy-policy.png)</kbd>

  5. When prompted to sign in, select **Azure AD – TechPass Prod**.

  ![gcc-cloudflare-access-signin](images/cloudflare-warp-macos/gcc-cloudflare-access-signin.png ':size=50%')

  ?>  If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

  6. Sign in using your TechPass credentials.

  ![techpass-sign-in](images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

  ?> If you are a public officer, you need to authorise your WOG sign-in first. To authorise that, enter the six-digit one-time password code displayed under your SG Govt M365 account on your authenticator app and then proceed to authorise your TechPass account.

  7. Once you have successfully signed in, click the Cloudflare WARP icon.

  <kbd>![cloudflare-warp-icon](images/onboarding-for-macos/cloudflare-icon.png)</kbd>

  The following screen is displayed.

  <kbd>![warp-teams](images/cloudflare-warp-macos/warp-teams.png)</kbd>

  ?>  If you need to connect to a different VPN, disconnect and quit from the WARP client.

</details>

If your onboarding is successful, within an hour, you will receive a successfully onboarded email to  your organisational email address.  

?> If you do not receive this email, please contact the [SEED team](mailto:gcc2.0_support@tech.gov.sg).

Shortly after this email, you will receive a desktop notification informing you that your device has been renamed and will automatically restart in the next five minutes. When you log in again, you will be prompted to reset your password. This is to enforce a strong password policy.
