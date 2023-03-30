# Post onboarding instructions for macOS 11 and 12

  After you onboard your Internet Device to SEED: 

  - [Ensure Full Disk Access(FDA) is enabled for SEED components](#ensure-full-disk-accessfda-is-enabled-for-seed-components)
  - [Turn on Cloudflare WARP for macOS](#turn-on-cloudflare-warp-for-macos)

## Ensure Full Disk Access(FDA) is enabled for SEED components

After onboarding, ensure FDA is enabled for the following SEED components:

  - Tanium Client
  - Microsoft Intune Agent
  - Microsoft Defender
  - Microsoft Defender ATP Security Extension 

### To verify FDA is enabled for the SEED components

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. From the left pane, choose **Full Disk Access**.
4. Click the lock icon at the bottom and use your Touch ID or enter your  password to unlock.

?> **Note**<br>If you were not prompted to reset device password while onboarding, you will be prompted now. See FAQ for password policy.

5. Ensure the following applications are listed and enabled (checkboxes should be selected):
    - Tanium Client
    - Microsoft Intune Agent
    - Microsoft Defender
    - Microsoft Defender ATP Security Extension 

![fda-enabled](../images/onboarding-for-macos/all-apps-fda-enabled.png ':size=75%')

?> **Note**<br>If a SEED component is missing, see [Common onboarding issues for macOS users](faqs/common-onboarding-issues) to resolve it.

## Turn on Cloudflare WARP for macOS

After you onboard your macOS Internet Device to SEED, you need to turn on Cloudflare WARP.

### To turn on Cloudflare WARP for macOS

[turn on Cloudflare WARP for macOS](../snippets/snippets-turn-on-cloudflare-warp-for-macos.md ':include')



