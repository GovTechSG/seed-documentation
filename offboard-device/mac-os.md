# Offboard macOS device from SEED


## Step 1: Remove your device from Microsoft Intune

  1. Open the **Company Portal** application and click **Sign in**.

  <kbd>![sign-in](../images/onboarding-for-macos/sign-in.png)</kbd>

  2. Log in using your TechPass account credentials.

     <kbd>![log-in-to-gcc](../images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

> **Note:**
>- Your two-factor authentication(2FA) varies based on the authentication method you have [set up](https://account.activedirectory.windowsazure.com/Proofup.aspx). If you're using the text message method for authentication, after you enter your password, enter the verification code sent to your phone.

  3. Go to **Devices** and click the three dots beside the device you want to unenrol.
  4. Choose **Remove**.

  <kbd>![devices](../images/onboarding-for-macos/devices-2.png)</kbd>
  5. When prompted to confirm the removal, select **Remove**.
  6. Click your profile icon and **Sign out** of **Company Portal**.

## Step 2: Remove Tanium Client

  1. Open the **Terminal** app and run the following commands:

  ```
  sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo launchctl remove com.tanium.taniumclient > /dev/null 2>&1

  sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

  sudo rm -rf /Library/Tanium/

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

  sudo rm /var/db/receipts/com.tanium.tanium.client.bom

  sudo rm /var/db/receipts/com.tanium.tanium.client.plist
  ```
2. Enter your macOS password when prompted.  

## Step 3: Remove Cloudflare WARP client

  1. Open the **Terminal**app and run the following command.

  ```
  sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
  ```
  2. Enter your macOS password when prompted.

## Step 4: Remove Microsoft Defender for Endpoint

To remove Microsoft Defender for Endpoint from your device, offboard your device from it using the offboarding package.

1. Open **Terminal** and run `mdatp health`.
2. Take note of the value displayed for **org_id**.
3. Identify the organisation corresponding to this **org_id** from the following table. This is the organisation of the Defender or the antivirus on your device.

  | org_id  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
  | 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

  > **Note**:
  > If your organisation id(org_id) is different from the above three, contact the respective MDM administrator or Defender administrator to get the offboarding script.

4. Based on the organisation, use your GMD to download the offboarding script from the following:

  | Organisation  | SEED offboarding script |
  | ------------- |:-------------:|
  | WOG      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/wog_mac)    |
  | TechPass      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/tp_mac)     |
  | Hive      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/hive_mac)     |

5. When prompted to log in, log in with your TechPass.

> **Note**: If you have any issues in accessing the link to download the offboarding script,
>- Make sure that you are using your GMD, device that was onboarded to SEED, to download the offboarding script.
>- Access the link in incognito mode.
>- Make sure you are using only the [supported browsers](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/additional-resources/best-practices?id=supported-browsers).
>- If you still have issues in downloading the script, create a [support request](https://go.gov.sg/seed-techpass-support).

6. Save the offboarding script to the **Downloads** folder.

> **Note**:
> Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, wog_mac_valid_until_2021-11-10.sh

7. Go to **Terminal** and run the following command:
  ```
  sudo /bin/sh ~/Downloads/name_of_offboarding_script.sh
  ```
>- **Note:**
> The file name *name_of_offboarding_script* in this command is only an example. When you run the command, specify the file name of the offboarding script you downloaded.


8. Go back to the **Finder** icon in the **Dock**.
9. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
10. Drag the app to the Bin, or select the app and choose **File** > **Move to Bin**.
