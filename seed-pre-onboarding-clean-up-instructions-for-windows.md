# SEED Pre-onboarding Clean-up Instructions (Windows)

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

**.\name\_of\_offboarding\_script.cmd**
