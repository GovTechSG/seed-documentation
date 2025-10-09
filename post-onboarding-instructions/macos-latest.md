# macOS post onboarding guide

After onboarding your Internet Device to SEED, follow these instructions:

- [Ensure Full Disk Access(FDA) is enabled for SEED components](#ensure-full-disk-accessfda-is-enabled-for-seed-components)
- [Turn on Cloudflare WARP for macOS](#turn-on-cloudflare-warp-for-macos)
- [Verify Microsoft Defender is configured](verify-microsoft-defender-is-configured)

## Ensure Full Disk Access (FDA) is enabled for SEED components

After onboarding, ensure FDA is enabled for the following SEED components:

- Tanium Client
- Microsoft Intune Agent
- Microsoft Defender
- Microsoft Defender ATP Security Extension 
- Falcon agent (Users who signed up after 22 August 2025)

**Verification steps**:

1. Go to the **Apple** menu > **System Settings**.  
2. On the left pane, select **Privacy & Security**.
3. If prompted, unlock the setting using your Touch ID or enter your device password.

> **Note**: If you were not prompted to reset device password during onboarding, you will be prompted now. Refer to the FAQ for password policy.

4. On the **Privacy & Security** pane, choose **Full Disk Access**.
  ![fda-enabled](../images/macosimage-1.png)

5. Ensure the following applications are listed and enabled:

    - Tanium Client
    - Microsoft Intune Agent
    - Microsoft Defender
    - Microsoft Defender Endpoint Security Extension
    - Falcon agent (Users who signed up after 22 August 2025)

  ![fda-enabled](../images/macosimage-2.png)

  >**Note**: If a SEED component is missing, refer to [Onboarding FAQ](/faqs/onboarding-faq).

## Verify CrowdStrike is configured

1. Open **Finder** → **Applications** → **Falcon.app**.
2. Ensure the **CrowdStrike Falcon Sensor** is **registered**, **operational**, and **cloud connected**.  

   ![CrowdStrike Falcon Sensor status](../images/macosimage-3.png)

3. If any of the above statuses indicate an error:
   -  Click **Configure Settings** and follow the steps as prompted.

   
## Turn on Cloudflare WARP

After onboarding your macOS Internet Device to SEED, you need to activate Cloudflare WARP.

**Activation steps**:

1. Open **Cloudflare WARP** client from the menu bar.

  ![cloudflare-warp-icon](../images/onboarding-for-macos/cloudflare-icon.png)
  
  You will see the information page, followed by the privacy policy.

2. Click **Next**, **Accept** to agree to Cloudflare’s privacy policy.

  ![accept-privacy-policy](../images/cloudflare-warp-macos/accept-privacy-policy.png)

3. When prompted to sign in, select **Azure AD – TechPass Prod**.

  ![gcc-cloudflare-access-signin](../images/cloudflare-warp-macos/gcc-cloudflare-access-signin.png ':size=50%')
  
  If you encounter an error stating that your user account is not found in the respective tenant, follow these instructions:

  - Open a new browser tab
  - Visit https://myaccount.microsoft.com
  - Sign out of your current account
  - Retry the action

4. Sign in using your TechPass credentials.

  ![techpass-sign-in](../images/cloudflare-warp-macos/techpass-sign-in.png ':size=50%')

5. After successfully signing in, click **Open Cloudflare WARP app** to establish your WARP connection.

Once connected, you should see WARP Zero Trust in the connected state.
  
  ![cf-warp-connected](../images/cloud-flare-connected.png ':size=50%')

6. Open Cloudflare WARP **Settings**, and ensure **Gateway with WARP** is selected. WARP is now active, safeguarding your Internet connection.

## Verify Microsoft Defender is configured

1. Open **Terminal** and run `mdatp health`.
2. Take note of the value displayed for **org_id**.

> **Note**: If this command does not return anything, it indicates your device does not have Defender. [Proceed to onboard your macOS device to SEED](/onboard-device/identify-onboarding-persona).

Identify the organisation corresponding to this **org_id** from the following table. This is the organisation of the Defender or the antivirus on your device.

| org_id  | Organisation |
| ------------- |:-------------:|
| faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
| 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
| 6389e966-e334-461d-86ce-0fed12484620      | Hive    |

4. Choose the required step from the following:

- If your organisation id corresponds to WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and you can ignore the rest of this section.

- If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to retrieve the offboarding package to unenrol your device. Refer to [Offboarding FAQ](faq/offboarding-faq.md) for more details.
    
 - If your device is enrolled with a different MDM, contact your organisation IT support to unenrol your device from it.

Within the next few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can sign in to Company Portal app, click the three dots and choose **Check status** to check for policy or profile updates. It may take a while to complete the synchronisation. When completed, the screen will show the timestamp of the last successful sync.
