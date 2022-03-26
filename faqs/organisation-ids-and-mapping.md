### Organisation IDs and organisation mapping

For any device to successfully onboarded to SEED it should be offboarded or unenrolled from the current antivirus or Defender ATP. Any anitvirus software or Defender ATP will be associated with an organisation and to unenroll the device from it, you need to contact the respective organisation and get the offboarding scripts for your device OS.

This section provides the list of possible organisation ids and their names.

<!--To identify if Defender ATP or any other antivirus is running on a device, macOS users will run `mdatp health` on their **Terminal**.

Windows users will open **Registry Editor** to run as administrator and go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Protection** > **Status**.

This will help you identify the organisation id of the Defender ATP or the antivirus currently running on the device. Once you locate the organisation, get the offboarding scripts from the respective MDM Administrator or Defender Administrator.-->

| org_id  | Organisation |
| ------------- |:-------------:|
| faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
| 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
| 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

?> If the org_id is different from the above three, contact the respective MDM administrator to get the offboarding script.

**Related topics**
- [Pre onboarding instructions for macOS users](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-pre-onboarding-clean-up-instructions-for-macos)
- [Pre onboarding instructions for Windows users](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-pre-onboarding-clean-up-instructions-for-windows)
