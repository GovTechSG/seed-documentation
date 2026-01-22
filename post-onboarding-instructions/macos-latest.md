# macOS post onboarding guide

After onboarding your Internet Device to SEED, follow these instructions:

- [Ensure Full Disk Access(FDA) is enabled for SEED components](#ensure-full-disk-accessfda-is-enabled-for-seed-components)
- [Turn on Cloudflare WARP for macOS](#turn-on-cloudflare-warp-for-macos)

## Ensure Full Disk Access (FDA) is enabled for SEED components

After onboarding, ensure FDA is enabled for the following SEED components:

- Tanium Client
- Microsoft Intune Agent
- Falcon agent 

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
    - Falcon agent 

  ![fda-enabled](../images/macosimage-2.png)

  >**Note**: If a SEED component is missing, refer to [Onboarding FAQ](/faqs/onboarding-faq).


### Known issue: Full Disk Access (FDA) on macOS 26

There is a known issue on **macOS 26** where **Tanium** does not appear in the **Full Disk Access (FDA)** settings page, even after it has been added.

**Workaround**:

1. Go to **System Settings** → **Privacy & Security** → **Full Disk Access**.
2. Drag and drop **TaniumClient** into the Full Disk Access page.

[fda-enabled](../images/fda-macos26.png)

> **Note**: Due to a macOS bug, **Tanium will still not be visible** in the FDA list after being added.  
> Full Disk Access is **successfully granted**, and Tanium will continue to function as expected.
