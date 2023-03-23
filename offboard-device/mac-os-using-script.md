# Offboard macOS device using a script
 
 This document guides you to offboard your macOS device onboarded to SEED.

## Audience

- Users who need to offboard their macOS device from SEED.

## Prerequisites

- You must have an active TechPass account.
- Your device must have been onboarded to SEED.
- [Optional] We recommend you to have your Intune device ID ready. 

## Get Intune Device ID

[Get Intune Device ID](../snippets/get-intune-device-id.md ':include')

!> **Note**<br>If you have any issues with the offboarding steps, see the [Offboarding FAQ](/faqs/seed-offboarding-faqs) before submitting an [incident request](https://go.gov.sg/techpass-sr) with TechPass support.

## Phase A: Offboard device from SEED components

1. Go to **Terminal** and run `mdatp health`.

<!--
![open terminal](../images/macos-open-terminal.png)

![find-org-id](../images/macos-find-org-id-1.png)-->

2. Take note of the value displayed for **org_id**.

![note-org-id](../images/macos-find-org-id-2.png)

3. Refer to the following table and identify your **Defender organisation** and download the respective offboarding script.

  | org_id  | Defender organisation | Offboarding script |
  | ------------- |:-------------:|:-------------:| 
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_wog_mac)    |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_tp_mac)     | 

!> **Important**<br> If your Defender organisation is neither **WOG** nor **TechPass**, contact the IT support of the organisation that provided you with the device.

 
4. Go to the folder where you downloaded the ZIP file and extract the files. You should see the following two files. 

![extract-files](../images/macos-extracted-files-for-offboarding.png)

?> **Note**: The file names vary with the organisation.

5. On your **Terminal**, go to the folder where you extracted the files. For example, if they are in the **Downloads** > **Offboarding_local_wog_mac** folder, go to that folder.

![cd-extracted-folder](../images/macos-cd-downloads.png)

6. Copy and run the following command on your **Terminal**.

    ```sudo chmod +x local_mac_offboarding.sh```

7. When prompted for a **Password**, enter your device password.
8. Copy and run the following command on your **Terminal**.

    ```sudo ./local_mac_offboarding.sh```

When you see the following success message on your **Terminal**, you are automatically directed to the **SEED Offboarding: Device Record Removal** form to submit the Intune Device ID. 

![macos-success-message](../images/macos-success-message.png)

!>**Important note**<br> Make sure you complete the steps in Phase 2 immediately after Phase 1. If not, your device update policy may push the latest version of the deleted SEED components.


## Phase B: Submit Intune Device ID

### Prerequisites

a. Successful completion of [Phase A: Offboard device from SEED components](#phase-a-offboard-device-from-seed-components).
b. **Intune Device ID**. Generally, when you successfully offboard your device from the SEED components, the Intune Device ID is automatically displayed on the **SEED Offboarding: Device Record Removal** form. If it is not displayed, see [Get Intune Device ID](#get-intune-device-id).

c. [Optional]If you had submitted an incident request with the TechPass support team to offboard your device from the SEED components, please have the reference number ready as we may need this information.

### To submit Intune Device ID

1. Ensure your **Intune Device ID** is displayed on the form. If it is not displayed, provide it.
2. Enter your organisational email address in **Organisational Email Address** and click **Verify**.
3. Enter the OTP you receive at this email address.  
4. Indicate if you had any issues while completing [Step 1: Offboard device from SEED components](#step-1-offboard-device-from-seed-components).
5. [Optional] If you had issues completing **Phase A**, we encourage you to provide the **Support Ticket Number**.
6. Click **Submit**. When this request is processed successfully, we send a notification via email.

<!--![successfully-offboarded-email](../images/macos-successfully-offboarded-email.png)-->

?> **Additional information**<br>- We need 30 minutes to process your ticket.<br>- If you are still waiting to receive an email after 30 minutes, please submit a [TechPass support request](https://go.gov.sg/techpass-sr). 

 
      










 



