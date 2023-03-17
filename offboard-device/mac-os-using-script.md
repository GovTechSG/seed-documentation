# Offboard macOS device using a script

[Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components)

[Step 2: Submit Intune Device ID](#step-2-submit-intune-device-id)

## Step 1: Offboard device from SEED components 

In this step, you need to run the scripts to remove the SEED components, such as Intune, Tanium, Defender and WARP, from your macOS device. 

In addition, it also resets some of the security configurations which were changed while onboarding the device to SEED.

### To offboard SEED components from macOS

1. Press ```Command+Spacebar``` and enter **Terminal.app**.

![open terminal](../images/macos-open-terminal.png)

2. On the **Terminal**, run `mdatp health` to find if your organisation is WOG or TechPass.

![find-org-id](../images/macos-find-org-id-1.png)

3. Take note of the value displayed for **org_id**.

![note-org-id](../images/macos-find-org-id-2.png)

4. Refer to the following table and find the Defender's organisation on your device.

  | org_id  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    | 

!> **Important**<br> If your organisation ID is neither **WOG** nor **TechPass**, you can only use [**Method 2**](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/offboard-device/mac-os) for offboarding your device from SEED.

5. Download the offboarding package(ZIP file) for your organisation.

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

When you see the following success message on your **Terminal**, you are automatically directed to the **SEED offboarding Device Form** to proceed to submit the Intune Device ID to complete the offboarding from the server side.

![macos-success-message](../images/macos-success-message.png)


## Step 2: Submit Intune Device ID

!>**Things to note**<br>- When you successfully complete [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components) , you will be automatically directed to the **SEED offboarding Device Form**.<br>- If you can't or need help to complete the local offboarding, go to the [SEED offboarding Device Form](https://form.gov.sg/63c62c20d4e11c0012f59e90) and complete the following steps.

### Prerequisites

**Intune Device ID** of the device. 

By default, when you complete [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components), your Intune Device ID is automatically displayed on the form. If it is not displayed, complete the appropriate step to get your **Intune Device ID**:

- If you can access the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile), get the Intune Device ID from your account profile.
- If you can't access the TechPass portal, please submit a [TechPass service request](https://form.gov.sg/5f69797d0666cb0011cc59da) to get your Intune Device ID.

### To submit Intune Device ID

1. Ensure your **Intune Device ID** is displayed on the form. If it is not displayed, see the [prerequisites](#prerequisites) section.
2. Enter your organisational email address in **Work Email Address** and click **Verify**.
3. Enter the OTP you receive at this email address.  
4. Indicate if you successfully completed [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components).
5. If you had issues completing it, upload the supporting information as evidence.
6. Click **Submit**. When this request is processed successfully, we send a notification via email.

![successfully-offboarded-email](../images/macos-successfully-offboarded-email.png)

?> **Additional information**<br>- We need 30 minutes to process your ticket.<br>- If you do not receive any email after 30 minutes, please submit a [TechPass support request](https://form.gov.sg/5f69797d0666cb0011cc59da).

 
      










 



