# Offboard macOS device using a script


[Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components)

[Step 2: Submit Intune Device ID](#step-2-submit-intune-device-id)

## Step 1: Offboard device from SEED components

!> **Important note**<br>If you are unable to complete the following steps, see the FAQs. If you still experience any issues, please submit an [incident request](https://go.gov.sg/techpass-sr).  

1. Press ```Command+Spacebar``` and enter **Terminal.app**.

![open terminal](../images/macos-open-terminal.png)

2. On the **Terminal**, run `mdatp health` to find if your organisation is WOG or TechPass.

![find-org-id](../images/macos-find-org-id-1.png)

3. Take note of the value displayed for **org_id**.

![note-org-id](../images/macos-find-org-id-2.png)

4. Refer to the following table and find your Defender's organisation.

  | org_id  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    | 

!> **Important**<br> If your Defender organisation is neither **WOG** nor **TechPass**, contact the IT support of the organisation that provided you the device.

5. Download the offboarding script, a ZIP file, for your Defender organisation.

  | Organisation  | SEED offboarding script |
  | ------------- |:-------------:|
  | WOG      | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_wog_mac)    |
  | TechPass      | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_tp_mac)    |
  
6. Go to the folder where it was downloaded and extract the files from the ZIP file. You should see the following two files. 

![extract-files](../images/macos-extracted-files-for-offboarding.png)

?> **Note**: The file names vary with the organisation.

7. On your **Terminal**, go to the folder which has the extracted files. For example, if they are in the **Downloads** > **Offboarding_local_wog_mac** folder, go to that folder.

![cd-extracted-folder](../images/macos-cd-downloads.png)

8. Copy and run the following command on your **Terminal**.

    ```sudo chmod +x local_mac_offboarding.sh```

9. When prompted for a **Password**, enter your device password.
10. Copy and run the following command on your **Terminal**.

    ```sudo ./local_mac_offboarding.sh```

When you see the following success message on your **Terminal**, you are automatically directed to the **SEED offboarding: Request to remove device record** form to submit the Intune Device ID. 

![macos-success-message](../images/macos-success-message.png)

!>**Important note**<br> Make sure you complete Step 2 immediately after Step 1. If not, your device update policy can push the latest version of the deleted SEED components.


## Step 2: Submit Intune Device ID

### Prerequisites

1. Successful completion of [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components).
2. Intune Device ID. Generally, when you successfully offboard your device from the SEED components, the Intune Device ID is  automatically displayed on the **SEED offboarding: Request to remove device record** form.

?>**Note**<br>- If Intune Device ID is not displayed, complete the appropriate step:<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) and get the Intune Device ID from your account profile.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- If you can't access the TechPass portal, please submit an [incident request](https://go.gov.sg/techpass-sr) to get your Intune Device ID before proceeding further.

3. [Optional]If you had submitted an incident request with TechPass support team to offboard your device from the SEED components, please have the reference number ready as we may need this information.

### To submit Intune Device ID

1. Ensure your **Intune Device ID** is displayed on the form. If it is not displayed, see the [prerequisites](#prerequisites) section.
2. Enter your organisational email address in **Work Email Address** and click **Verify**.
3. Enter the OTP you receive at this email address.  
4. Indicate if you had any issues while completing [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components).
5. [Optional] If you had issues completing it, provide the  **Support Ticket Number**.
6. Click **Submit**. When this request is processed successfully, we send a notification via email.

<!--![successfully-offboarded-email](../images/macos-successfully-offboarded-email.png)-->

?> **Additional information**<br>- We need 30 minutes to process your ticket.<br>- If you do not receive any email after 30 minutes, please submit a [TechPass support request](https://go.gov.sg/techpass-sr).

 
      










 



