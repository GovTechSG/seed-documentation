**SEED Offboarding Instructions (Windows)**

This set of offboarding instructions is meant for **existing SEED users** to offboard their devices. If you are a new SEED user looking to ensure a clean device state prior to onboarding, please refer to the **SEED pre-enrollment clean-up instructions** instead.

**(1) Unenroll your**  **device from Intune**

1. Under &quot;Settings \&gt; Accounts \&gt; Access work or school&quot;, select &quot;Disconnect&quot;under your account.

**(2) Remove the Tanium Client**

1. Under &quot;Settings \&gt; Apps&quot;, search for &quot;Tanium Client&quot; and then select &quot;Uninstall&quot;

**(3) Remove the Cloudflare WARP client**

1. Under &quot;Settings \&gt; Apps&quot;, search for &quot;Cloudflare WARP&quot; and then select &quot;Uninstall&quot;.

**(4) Offboard from and uninstall Microsoft Defender ATP**

1. **For public officers,**** please approach the GCC2.0 team to request for the specific Defender ATP offboarding script for your OS. For vendors, please approach your Defender ATP admins to obtain your offboarding scripts.**
2. Place the offboarding script in your &quot;Downloads&quot; folder.
3. Go to &quot;Start&quot; and type &quot;cmd&quot;.
4. In the matches that appear, right-click on &quot;Command Prompt&quot;and select &quot;Run as administrator&quot;. Enter your Windows password if prompted.
5. Copy the following 2 commands into the &quot;Command Prompt&quot; window and click &quot;Enter&quot;. You may have to wait for around 30 seconds for the second command to finish executing:

**cd &quot;%USERPROFILE%\Downloads\&quot;**

**.\name\_of\_offboarding\_script.cmd**
