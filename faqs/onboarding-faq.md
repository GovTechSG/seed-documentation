# Onboarding FAQ

## ✅ Onboarding confirmation and errors

<details>
  <summary>How can I confirm the successful onboarding of my Internet Device to SEED?</summary>
  After completing the onboarding process, you should receive a confirmation email within two hours. If not, [raise a service request](https://go.gov.sg/seed-techpass-support).
</details>

<details>
  <summary>I did not receive the successfully onboarded email after onboarding to SEED. What should I do?</summary>
  Possible reasons:

  - Microsoft Defender or any other antivirus solution previously installed on the device was not completely removed before onboarding to SEED.
  - Tanium and Cloudflare were not installed while onboarding to SEED.

  Before raising a service request, confirm the following:
  - Verify if Microsoft Defender is configured correctly on your device.
  - Check if Tanium and Cloudflare are installed. These applications should be automatically installed during device enrolment with SEED. If they are not installed, [raise a service request](https://go.gov.sg/seed-techpass-support).
</details>

<details>
  <summary>What should I do if my device is not automatically renamed after SEED onboarding?</summary>
  This can happen if Defender or any other antivirus already installed on the device was not completely removed before onboarding to SEED. To confirm this, verify if Microsoft Defender is configured correctly on your device.
</details>

<details>
  <summary>What should I do if my onboarding status to SEED shows as 'Failed' due to Tanium issues?</summary>
  Possible reasons for a failed onboarding status include:

  - **Failed (Tanium not installed or configured incorrectly)**: Tanium was either not installed or set up properly.
  - **Failed (Error occurred while tagging device as onboarded)**: An issue occurred while tagging the device as onboarded in Tanium.
  - **Failed (Error occurred while installing endpoint identity tools)**: An error occurred during the installation of the endpoint identity tools.

  To resolve the issue, follow these steps:

  (Troubleshooting steps for mac (Intel), mac (Apple chip), and Windows...)

  If the issue persists after following these steps, please raise an [incident support request](https://go.gov.sg/seed-techpass-support).
</details>

## 🔧 Troubleshooting setup issues

<details>
  <summary>What should I do if profile installation fails during management profile installation?</summary>
  1. Ensure you have received an email confirming that the required SEED onboarding license has been assigned to you. If you have received this confirmation, proceed to step 2.
  2. Navigate to the **Apple** menu > **System Preferences** > **Profiles**.
  3. If you already have an existing **Management Profile**, select it and remove it by clicking the minus icon.
  4. If you encounter difficulties removing the **Management Profile**, uninstall **Company Portal**.
  5. Reinstall [Company Portal](https://go.microsoft.com/fwlink/?linkid=853070).
  6. [Onboard your device to SEED](onboard-device/identify-onboarding-persona).
</details>

<details>
  <summary>While onboarding to Microsoft Intune, I receive an error message: "Could not download the identity profile from the Encrypted Profile Service."</summary>
  One possible reason is your device may have been previously onboarded by another user and was not properly offboarded.  
  Raise a [service request](https://go.gov.sg/seed-techpass-support) with your serial number and follow relevant offboarding steps.
</details>

<details>
  <summary>What should I do if my onboarding fails while registering my Intune Device ID on the TechPass portal?</summary>

  | Reason for failed onboarding | Action required |
  | ---|---|
  | Unexpected Error | [Raise a service request](https://go.gov.sg/seed-techpass-support). |
  | Software Misconfiguration Error | [Raise a service request](https://go.gov.sg/seed-techpass-support). |
  | Endpoint Error | Ensure stable internet > Go to [TechPass Portal](https://portal.techpass.gov.sg) > My Account > SEED Devices > Retry. |
  | Software Installation Error | Restart your device > Retry steps above. |
  | Internal Error | Restart your device > Retry steps above. |
  | DWP device used | You cannot onboard DWP devices. Only Internet Devices are supported. |
</details>

<details>
  <summary>While approving the management profiles, I get a message "Profiles cannot be approved while using remote or automated input method". What should I do?</summary>
  To resolve this issue, upgrade to the [latest macOS version][upgrade-macos] and ensure your Mac has sufficient available disk space before attempting to approve the profiles.
</details>

## 🔐 Full Disk Access and FileVault

<details>
  <summary>While enabling Full Disk Access (FDA), I could not find <b>TaniumClient</b>. What should I do?</summary>
  Run this command in Terminal: `sudo chmod 755 /Library/Tanium/TaniumClient`  
  Then manually add **TaniumClient** to **Full Disk Access** under **Security & Privacy**.
</details>

<details>
  <summary>While enabling Full Disk Access (FDA), I cannot find <b>Microsoft Intune Agent</b> and <b>Microsoft Defender for Endpoint</b>. What should I do?</summary>
  Add them manually:
  - **Microsoft Intune Agent**: `/Library/Intune/Microsoft Intune Agent.app`
  - **Defender**: `/Applications/Microsoft Defender for Endpoint`
</details>

<details>
  <summary>While enabling Full Disk Access (FDA), I cannot find <b>Microsoft Defender Endpoint Security Extension</b>. Can I proceed with onboarding?</summary>
  Yes, continue with onboarding. It should appear within four hours. If not, [raise a service request](https://go.gov.sg/seed-techpass-support).
</details>

<details>
  <summary>When enabling FileVault or FDA, I am unable to unlock Security & Privacy preferences using my current password. What should I do?</summary>
  1. Go to the **Apple** menu > **Lock Screen** or press **Command+Control+Q**.  
  2. Enter your password.  
  3. Follow the prompt to reset your password.
</details>

## 🛡️ CrowdStrike

<details>
  <summary>Falcon sensor is not registered, not operational or not cloud connected.</summary>
  **macOS**:  
  1. Go to **Apple menu** > **System Settings**.  
  2. Click **Privacy & Security**.  
  3. Unlock if prompted.  
  4. Enable **Full Disk Access** for **Falcon**.
</details>

<details>
  <summary>Falcon sensor is not pushed down.</summary>
  1. Ensure you have the SEED License assigned to you in the [TechPass Portal](https://portal.techpass.gov.sg).  
  2. Sync your device:
     - **macOS**: Open Company Portal, click three dots → **Check status**
     - **Windows**: Access work/school → Info → **Sync**
  3. Restart your computer.
</details>
