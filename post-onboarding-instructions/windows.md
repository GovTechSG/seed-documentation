# SEED post onboarding instructions for Windows

After you onboard your Internet Device to SEED, [Turn on Cloudflare WARP for Windows](#turn-on-cloudflare-warp-for-windows).

## Turn on Cloudflare WARP for Windows

1. [Download the latest Cloudflare WARP client](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-windows-1/distribution_groups/release) for Windows. 

2. Go to your download folder and open the executable file to install WARP.
3. Follow the on screen instructions and grant the appropriate permissions to complete the installation. 

4. If your device is connected to any other VPN, disconnect it as it might clash with Cloudflare WARP.

<!--5. Click the **Show hidden icons** arrow next to the notification area and make sure that Cloudflare WARP icon is displayed on your device or go to the **Start** menu and search for **Cloudflare WARP**.

![](../images/cloudflare-warp-windows/check-cloudflare-warp-desktop-client.png ':size=400')-->

5. Open the Cloudflare WARP client. You will see the information page, followed by the privacy policy.

6. Click **Next** and then **Accept** to agree to the Cloudflare’s privacy policy.

![cloudflare-for-teams](../images/cloudflare-warp-windows/cloudflare-for-teams.png ':size=400')

7. When prompted to sign in, choose **Azure AD – TechPass Prod**.

![azure-ad-techpass-prod](../images/cloudflare-warp-windows/azure-ad-techpass-prod.png ':size=400')

  > **Note** 
  > 
  > If you encounter an error stating that user account does not exist in the respective tenant, open a new tab and go to [https://myaccount.microsoft.com](https://myaccount.microsoft.com/), sign out from your account and then retry.

8. Sign in using your TechPass credentials.

![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

9. After successfully signing in, click **Open Cloudflare WARP.app**.

When the device is connected to WARP, you should see the WARP Zero Trust in the connected state.
  
![after-signed-in](../images/cloudflare-warp-windows/after-signed-in.png ':size=400')

10. Open Cloudflare WARP **Settings**, and make sure **Gateway with WARP** is selected.

WARP is now running and protecting your Internet connection.
  







<!--
**Enrol in Cloudflare using WARP client to access protected engineering resources**

1. Click the **Show hidden icons** arrow next to the notification area and make sure that Cloudflare WARP icon is displayed on your device or go to the **Start** menu and search for **Cloudflare WARP**.

<kbd>![](../images/cloudflare-warp-windows/check-cloudflare-warp-desktop-client.png ':size=400')</kbd>

?> If it is not available on your device, install it from [Cloudflare App Center](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-windows-1/distribution_groups/release).

2. Disconnect from any other VPN that might be running as that could clash with Cloudflare.

3. Run the Cloudflare WARP client. You will see an information page, followed by a privacy policy.

4. Click **Next** and accept the policy.

<kbd>![cloudflare-for-teams](../images/cloudflare-warp-windows/cloudflare-for-teams.png ':size=400')</kbd>

3. When prompted to sign in, choose **Azure AD – TechPass Prod**.

![azure-ad-techpass-prod](../images/cloudflare-warp-windows/azure-ad-techpass-prod.png ':size=400')

5. Sign on using your TechPass credentials.

6. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. However, if you are a public officer, you must first approve your WOG login before approving your Techpass login.

<kbd>![techpass-sigin](../images/cloudflare-warp-windows/techpass-sigin.png ':size=400')</kbd>

6. Once you have successfully signed in, click the Cloudflare WARP icon. You should see the following page.

<kbd>![after-signed-in](../images/cloudflare-warp-windows/after-signed-in.png ':size=400')</kbd>


?> The WARP client connects your device to the Cloudflare network, which functions like a VPN. If you want to connect to a different VPN, first turn off WARP connection before connecting to other VPN network. WARP will be automatically turned on after three hours and this will affect your other VPN connections.-->
