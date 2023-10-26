# Windows post onboarding guide

After onboarding your Internet Device to SEED, follow these instructions:

- [Turn on Cloudflare WARP for Windows](#turn-on-cloudflare-warp-for-windows)
- [Verify Microsoft Defender is configured](verify-microsoft-defender-is-configured)

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

## Verify Microsoft Defender is configured

1. Go to the **Start** menu and enter **Powershell**.
2. Right-click on the search result for **PowerShell** and select **Run as Administrator**.

![open powershell](/images/offboarding-windows/run_powershell.png)

3. On **Powershell**, run the following command:

```
$reg64 = [Microsoft.Win32.RegistryKey]::OpenBaseKey([Microsoft.Win32.RegistryHive]::LocalMachine, [Microsoft.Win32.RegistryView]::Registry64)
$OrgID =  $reg64.OpenSubKey("SOFTWARE\MICROSOFT\Windows Advanced Threat Protection\Status").GetValue("OrgID")
echo $OrgID
```
4. Take note of the value displayed for **OrgID**.

![find-org-id](/images/offboarding-windows/org_id_win.png)

?> Note: If you do not receive any response, it means you do not have Defender installed on your device. You can skip the steps in this section. [Proceed to onboard your Windows device to SEED](/onboard-device/identify-onboarding-persona).

5. Identify the organisation corresponding to this **OrgId** from the following table. This is the organisation of the Defender or the antivirus on your device.

  | OrgId  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
  | 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

6. Choose the required step from the following:

  - If your organisation id corresponds to WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and you can ignore the rest of this section.

  - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to get the offboarding package to unenrol your device. Refer to [offboarding FAQ](/faq/offboarding-faq.md) for more details.
    
  - If your device is enrolled with a different MDM, contact your organisation IT support to unenrol your device from it.

Within the next few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can manually sync by going to **Start** > **Settings** > **Accounts** > **Access work or school** > **Work or School Account** > **Info** > **Sync**. Alternatively, Open the Company Portal app on your device, go to **Settings** > **Sync**. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.
















