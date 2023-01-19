# SEED post onboarding instructions for macOS 11 (Big Sur) and 12 (Monterey)

## Enable Full Disk Access(FDA)

After onboarding, enable FDA for the applications installed during SEED onboarding.

**To enable FDA for the installed applications:**

  1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  2. Click the **Privacy** tab.
  3. From the left pane, choose **Full Disk Access**.
  4. Click the lock icon at the bottom and use your Touch ID or enter your  password to unlock.

  > **Note:**
  >
  > If you are unable to access this preference with your current password, complete the following steps to reset your device password:
  >1. Go to the **Apple** menu > **Lock Screen** or use keyboard shortcut **Command+Control+Q**.
  >2. Enter your password and press <b>return</b>. You will be prompted to reset password.
  >3. Reset your password.

  5. Ensure the following applications are listed:
       - Tanium Client
       - Microsoft Intune Agent
       - Microsoft Defender
       - Microsoft Defender ATP Security Extension <!--Microsoft Defenders Endpoint Security Extension-->


> **Note:** If any of the listed application is missing, please refer to [Common onboarding issues for macOS users](faqs/common-onboarding-issues).

  6. Select the checkboxes beside these applications.

   <kbd>![fda-enabled](../images/onboarding-for-macos/all-apps-fda-enabled.png)</kbd>


## Enrol with Cloudflare using WARP client

After onboarding to SEED, enrol your device with Cloudflare using WARP client to connect to protected engineering resources.


 1. [Download the latest WARP client](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-macos-1/distribution_groups/release) for macOS from the available Cloudflare WARP release builds.

> **Note**
  >- Make sure that you download the WARP client from the correct location.
  >- Verify if the download has not been modified.
  >- Grant the appropriate permissions to complete the installation.

  2. Follow the on screen instructions and install the WARP client.
  3. Disconnect from any other VPN that might be running as that could clash with Cloudflare WARP.
  4. Open the Cloudflare WARP client from the menu bar on the top right corner of your Mac device.

  <kbd>![cloudflare-warp-icon](../images/onboarding-for-macos/cloudflare-icon.png)</kbd> 
  
  You will see the information page, followed by the privacy policy.

  5. Click **Next** and then **Accept**.

  <kbd>![accept-privacy-policy](../images/cloudflare-warp-macos/accept-privacy-policy.png)</kbd>

  6. When prompted to sign in, select **Azure AD – TechPass Prod**.

  ![gcc-cloudflare-access-signin](../images/cloudflare-warp-macos/gcc-cloudflare-access-signin.png ':size=50%')

  > **Note** 
  > 
  > If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

  7. Sign in using your TechPass credentials.

  ![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

  8. Once you have successfully signed in, click **Open Cloudflare WARP.app** to get your WARP connected.

  When it is connected, you should see the following page.
  
  ![cf-warp-connected](../images/cloudflare-warp-connected.png ':size=50%')
  



<!--

After onboarding to SEED, enrol your device with Cloudflare using WARP client to connect to protected engineering resources.

**To enrol with Cloudflare WARP:**

  1. Ensure that you have Cloudflare WARP client installed in your device. If not, install the latest [Cloudflare WARP](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-macos-1/distribution_groups/release) version.

  2. Disconnect from any other VPN that might be running as that could clash with Cloudflare.

  3. Open the Cloudflare WARP client from the menu bar on the top right corner of your Mac device.

  <kbd>![cloudflare-warp-icon](../images/onboarding-for-macos/cloudflare-icon.png)</kbd>

  ?>  You can also press ``Command+Spacebar`` and search for  **Cloudflare WARP** application to open it.


 You will see the information page, followed by your privacy policy.

  4. Click **Next** and then **Accept**.

  <kbd>![accept-privacy-policy](../images/cloudflare-warp-macos/accept-privacy-policy.png)</kbd>

  5. When prompted to sign in, select **Azure AD – TechPass Prod**.

  ![gcc-cloudflare-access-signin](../images/cloudflare-warp-macos/gcc-cloudflare-access-signin.png ':size=50%')

  ?>  If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

  6. Sign in using your TechPass credentials.

  ![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

  ?> If you are a public officer, you need to authorise your WOG sign-in first. To authorise that, enter the six-digit one-time password code displayed under your SG Govt M365 account on your authenticator app and then proceed to authorise your TechPass account.

  7. Once you have successfully signed in, click the Cloudflare WARP icon.

  <kbd>![cloudflare-warp-icon](../images/onboarding-for-macos/cloudflare-icon.png)</kbd>

  The following screen is displayed.

  <kbd>![warp-teams](../images/cloudflare-warp-macos/warp-teams.png)</kbd>

  ?> The WARP client connects your device to the Cloudflare network, which functions like a VPN. If you want to connect to a different VPN, first turn off WARP connection before connecting to other VPN network. WARP will be automatically turned on after three hours and this will affect your other VPN connections.

  -->
