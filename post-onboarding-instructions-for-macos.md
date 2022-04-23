<!--# Post onboarding instructions for macOS users


<details>
  <summary>a. Enable Full Disk Access(FDA) for the applications installed for SEED</summary><br>

  1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  2. Click the **Privacy** tab.
  3. From the left pane, choose **Full Disk Access**.
  4. Click the lock icon at the bottom and use your Touch ID or enter your  password to unlock.

  <div class="warn">
  <p>If you are unable to access this preference with your current password, complete the following steps to reset your device password.</p>
 <ol>

  <li>Go to the <b>Apple</b> menu > <b>Lock Screen</b> or use keyboard shortcut <b>Command+Control+Q</b> .</li>
  <li>Enter your password and press <b>return</b>. You will be prompted to reset password.</li>
  <li>Reset your password.</li>
  </ol>
  </div>

  5. Ensure the following applications are listed:
       - Tanium Client
       - Microsoft Intune Agent
       - Microsoft Defender
       - Microsoft Defender ATP Security Extension <!--Microsoft Defenders Endpoint Security Extension-


  ?>  If any of the listed application is missing, please refer to [Common onboarding issues for macOS users](faqs/common-issues-while-onboarding-using-macos).

  6. Select the checkboxes beside these applications.

   <kbd>![fda-enabled](images/onboarding-for-macos/all-apps-fda-enabled.png)</kbd>


</details>
<details>
  <summary>b. Enrol on Cloudflare using WARP client to connect to protected engineering resources</summary><br>


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
-->
