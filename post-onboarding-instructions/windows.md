# SEED post onboarding instructions for Windows

After you onboard your Windows Internet Device to SEED, you need to turn on Cloudflare WARP.

## Turn on Cloudflare WARP for Windows

!> Make sure your device is **not connected** to any other VPN, as it might clash with Cloudflare WARP.

### To turn on Cloudflare WARP for Windows

1. Open the Cloudflare WARP client from the Windows Taskbar. You will see the information page, followed by the privacy policy.

2. Click **Next** and then **Accept** to agree to the Cloudflare’s privacy policy.

  ![cloudflare-for-teams](../images/cloudflare-warp-windows/cloudflare-for-teams.png ':size=400')

3. When prompted to sign in, choose **Azure AD – TechPass Prod**.

  ![azure-ad-techpass-prod](../images/cloudflare-warp-windows/azure-ad-techpass-prod.png ':size=400')

  !> **Note**<br> If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

4. Sign in using your TechPass credentials.

  ![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

5. After successfully signing in, click **Open Cloudflare WARP.app**.

  When the device is connected to WARP, you should see the WARP Zero Trust in the connected state.
  
  ![after-signed-in](../images/cloudflare-warp-windows/after-signed-in.png ':size=400')

6. Open Cloudflare WARP **Settings**, and make sure **Gateway with WARP** is selected.

  WARP is now running and protecting your Internet connection.
  







