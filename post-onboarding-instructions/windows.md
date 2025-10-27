# Windows post onboarding guide

After onboarding your Internet Device to SEED, follow these instructions:

- [Turn on Cloudflare WARP for Windows](#turn-on-cloudflare-warp-for-windows)

## Turn on Cloudflare WARP for Windows

>**Note**: Ensure that your device is not connected to any other VPN, as it might conflict with Cloudflare WARP.

**Activation steps**:

1. Open the Cloudflare WARP client from the Windows Taskbar. You will see the information page, followed by the privacy policy.

2. Click **Next**,then, **Accept** to agree to the Cloudflare’s privacy policy.

  ![cloudflare-for-teams](../images/cloudflare-warp-windows/cloudflare-for-teams.png ':size=50%')

3. When prompted to sign in, choose **Azure AD – TechPass Prod**.

  ![azure-ad-techpass-prod](../images/cloudflare-warp-windows/azure-ad-techpass-prod.png ':size=50%')

If you encounter an error stating that your user account is not found in the respective tenant, follow these instructions:

- Open a new browser tab
- Visit https://myaccount.microsoft.com
- Sign out of your current account
- Retry the action

4. Sign in using your TechPass login details.

  ![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

5. After successfully signing in, click **Open Cloudflare WARP app** to establish your WARP connection.

  When the device is connected to WARP, you should see the WARP Zero Trust in the connected state.
  
  ![after-signed-in](../images/cloudflare-warp-windows/after-signed-in.png ':size=50%')

6. Open Cloudflare WARP **Settings**, and ensure **Gateway with WARP** is selected. WARP is now active, safeguarding your Internet connection.



At any time, users can manually sync by going to **Start** > **Settings** > **Accounts** > **Access work or school** > **Work or School Account** > **Info** > **Sync**. Alternatively, Open the Company Portal app on your device, go to **Settings** > **Sync**. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.

## Verify CrowdStrike is configured

1. In the **Taskbar**, click the **CrowdStrike** icon.
2. Confirm that the **CrowdStrike Falcon Sensor** is:
   - **Running**
   - **Service is active**
   - **Cloud connected**  

   ![CrowdStrike Falcon Sensor status](../images/winimage-4.png)  
   ![CrowdStrike Falcon Sensor details](../images/winimage-5.png)

3. If any of the above statuses indicate an error:
   - Go to **Start** → **Settings** → **Accounts** → **Access work or school**.
   - Click the **Info** button next to your **TechPass** account.
   - Select **Sync**.
   - Restart your computer.















