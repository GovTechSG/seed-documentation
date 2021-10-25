# Get Microsoft Windows ready for onboarding

**Objective** : This section explains how to get your Microsoft Windows machine ready for SEED onboarding.

**Audience** :
- Public officers and vendors who intend to onboard using macOS.
- Defender ATP administrator who provides the scripts to vendors for offboarding from Microsoft Defender ATP.

Follow the below steps to get your device ready:
1. [Remove existing MDM software](#remove-existing-mdm-software)
2. [Remove Tanium Client](#remove-tanium-client)
3. [Remove pre-existing Cloudflare WARP client](#remove-pre-existing-cloudflare-warp-client)
4. [Offboard from Windows Defender for Endpoint](#offboard-from-windows-defender-for-endpoint)

## [Remove existing MDM software](#remove-existing-mdm-software)
Before proceeding to onboard, verify if your device is currently managed by any other MDM software and unenrol your device from it.

*To remove existing MDM software* :
1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Accounts**.
3. From the left menu, choose **Access work or school**.
<!-- image verify-mdm-->
If your device is managed by an MDM, your username in your organisation's domain will be displayed under **Work or school account**.
<!--image access-work-orschool-account-->
4. Click **Work or school account** and then click **Disconnect**.

## [Remove Tanium Client](#remove-tanium-client)
If Tanium Client is installed on your device, remove it before proceeding further.The below steps guide you how to verify its availability on your device and remove it.

*To remove Tanium Client* :
1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps** and search for **Tanium Client**.
3. If available, choose **Tanium Client** and then click **Uninstall**.

## [Remove pre-existing Cloudflare WARP client](#remove-pre-existing-cloudflare-warp-client)
If Cloudflare WARP client is installed on your device, remove it before proceeding further. The below steps guide you to verify its availability on your device and remove it.

*To remove Cloudflare WARP client* :
1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps** and search for **Cloudflare WARP**.
3. If available, choose **Cloudflare WARP** and then click **Uninstall**.

## [Offboard from Windows Defender for Endpoint](#offboard-from-windows-defender-for-endpoint)
1. In the search box on the taskbar, type **regedit**, then select **Registry Editor** from the results.  
2. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Policies** > **Microsoft**
3.Choose **Windows Advanced Threat Protection** and search for **OnboardingInfo**.
4. If available, [get the offboarding script](#get-offboarding-scripts-for-microsoft-defender-atp) for your device.
5. Save the offboarding script in the **Downloads** folder.
6. Type **cmd** in the search box on the taskbar.
7. Select **Command Prompt** and right-click to choose **Run as administrator**.
8. If prompted, enter your Windows password.
9. Run the below in the Command prompt.

 ```
 cd “%USERPROFILE%\Downloads\”
.\name_of_offboarding_script.cmd
  ```

  ### [Get offboarding scripts for Microsoft Defender ATP](#get-offboarding-scripts-for-microsoft-defender-atp)

  - If you are a Public Officer, [contact GCC2.0 team](gcc2.0_support@tech.gov.sg) to get the offboarding scripts.

  - If you are a vendor, contact your Defender ATP administrator to get the offboarding scripts.

  If you are a Defender ATP administrator, follow the below steps to get the offboarding scripts:

   1. Go to [Defender Security Center portal](https://securitycenter.windows.com/).

   2. Click **Settings** > **Devices** > **Offboard**.

   3. Select *Windows* as operating system and *Local Script* as **Deployment Method**.

<!--
  ### [Get offboarding scripts for Microsoft Defender ATP](#get-offboarding-scripts-for-microsoft-defender-atp)

  - If you are a Public Officer, [contact GCC2.0 team](gcc2.0_support@tech.gov.sg) to get the offboarding scripts.

  - If you are a vendor, contact your Defender ATP administrator to get the offboarding scripts. The Defender ATP administrator will do the following:


-->







<!--


## (1) Unenroll your device from existing Mobile Device Management (MDM) software

1. To check if your device is currently managed by MDM software, navigate to &quot;Settings \&gt; Accounts \&gt; Access work or school&quot; and verify that there is an entry titled &quot;Work or school account&quot; with a username below.
  1. If no entry exists, you can skip the rest of this section.
2. To ensure that you unenroll from any existing MDM software, click on the entry and select &quot;Disconnect&quot;.

## (2) Remove pre-existing Tanium Client

1. To check if the Tanium Client is installed on your device, navigate to &quot;Settings \&gt; Apps&quot; and verify that an app named &quot;Tanium Client&quot; exists.
  1. If no such app exists, you can skip the rest of this section
2. If the app exists, click on the entry and select &quot;Uninstall&quot;.

## (3) Remove pre-existing Cloudflare WARP client

1. To check if the WARP client is installed on your device, navigate to &quot;Settings \&gt; Apps&quot; and verify that an app named &quot;Cloudflare WARP&quot; exists.
2. If the app exists, click on the entry and select &quot;Uninstall&quot;.

## (4) Offboard from Defender for Endpoint

1. To check if Windows Defender is onboarded into Defender for Endpoint:
  1. Go to &quot;Start&quot; and search for an app called &quot;Registry Editor&quot;.
  2. Within the registry editor, navigate to the path &quot; **Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Policies\Microsoft**&quot;.
  3. Click on the subkey named &quot; **Windows Advanced Threat Protection**&quot; and verify the existence of a value named &quot; **OnboardingInfo**&quot;.
  4. If this value does not exist, Windows Defender is not onboarded into Defender for Endpoint and you can skip the rest of this section.
2. To offboard Windows Defender from the Defender for Endpoint service, obtain an **offboarding script** from your Defender Security Center administrator. Your administrator can follow steps a,b &amp; c below to obtain the script.
  1. This script can be found in the [Defender Security Center portal](https://securitycenter.windows.com/).
  2. Go to Settings \&gt; Device management \&gt; Offboarding and select Windows 10 as the operating system, with &quot;Local Script&quot; as deployment method.
  3. **This step is IMPORTANT** , please do not proceed without offboarding!
3. Place the offboarding script in your &quot;Downloads&quot; folder.
4. Go to &quot;Start&quot; and type &quot;cmd&quot;.
5. In the matches that appear, right-click on &quot;Command Prompt&quot;and select &quot;Run as administrator&quot;. Enter your Windows password if prompted.
6. Copy the following 2 commands into the &quot;Command Prompt&quot; window and click &quot;Enter&quot;. You may have to wait for around 30 seconds for the second command to finish executing:

**cd &quot;%USERPROFILE%\Downloads\&quot;**

**.\name\_of\_offboarding\_script.cmd** -->
