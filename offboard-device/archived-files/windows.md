# Offboard Windows device from SEED


## Step 1: Remove your  device from Microsoft Intune

1. Click **Start** icon on the taskbar.
2. Go to  **Settings** > **Accounts** > **Access work or school**.
3. Click your account and select **Disconnect**.

## Step 2: Remove the Tanium Client

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Tanium Client** and then select **Uninstall**

## Step 3: Remove the Cloudflare WARP client

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Cloudflare WARP** and then select **Uninstall**.

## Step 4: Remove Microsoft Defender for Endpoint

To remove Microsoft Defender for Endpoint from your device, offboard the device from it using the offboarding script.

  1. In the search box on the taskbar, type **regedit**.
  2. Choose **Registry Editor** from the results and click **Run as administrator**.
  3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**.
  4. Take note of the value displayed for **OrgId**.
  5. Identify the organisation corresponding to this **OrgId** from the following table. This is the organisation of the Defender or the antivirus on your device.

    | OrgId  | Organisation |
    | ------------- |:-------------:|
    | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
    | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
    | 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

    > **Note**:
    > If your organisation id(OrgId) is different from the above three, contact the respective MDM administrator or Defender administrator to get the offboarding script.

  6. Based on the organisation, use the GMD to download the offboarding script from the following:

  | Organisation  | Offboarding script |
  | ------------- |:-------------:|
  | WOG      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/wog_windows)    |
  | TechPass      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/tp_windows)     |
  | Hive      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/hive_windows)     |

  7. When prompted to log in, log in with your TechPass.

  > **Note**: If you have any issues in accessing the link to download the offboarding script,
  >- Make sure that you are using your GMD, device that was onboarded to SEED, to download the offboarding script.
  >- Access the link in incognito mode.
  >- Make sure you are using only the [supported browsers](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/additional-resources/best-practices?id=supported-browsers).
  >- If you still have issues in downloading the script, create a [support request](https://go.gov.sg/seed-techpass-support).

  8. Save the offboarding script in your **Downloads** folder.

   > **Note**:
   > Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *wog_windows_valid_until_2022-09-07.cmd*.

  9. Go to **Start** and type **cmd**.
  10. Right-click on **Command Prompt** and select **Run as administrator**.
  11. If prompted, enter your Windows password.
  12. Run the following commands:
     ```
     cd "%USERPROFILE%\Downloads\"

     .\name_of_offboarding_script.cmd
     ```
> **Note:**
> Name of the .cmd file mentioned in this command is only an example. When you run the command, specify the file name of the offboarding script you downloaded.  
