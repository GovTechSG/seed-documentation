# Offboarding FAQ

<details>
<summary>What should I do if I cannot download the offboarding package?</summary>

Raise a [support request](https://go.gov.sg/seed-techpass-support) and request the offboarding package for your Defender organisation.

</details>

<details>
<summary>What should I do if I am unable to log in to my device?</summary>

1. Raise a [support request](https://go.gov.sg/seed-techpass-support).
2. In **Details**, enter the text *I am unable to offboard my device from SEED components but I would like to submit my Intune Device ID to offboard my device from SEED*.
3. Select SEED as **TechPass Tenant**.
4. Select Production as **Environment**.
5. Provide all the required details and submit the form.

</details>

<details>
<summary>Why do I get the error <b>Unknown Tenant detected</b> while running the offboarding package?</summary>

This error indicates that you are not a SEED user or your device was not properly enrolled in SEED.

If you had properly onboarded your device to SEED earlier but still get this error, please r[aise a service request](https://go.gov.sg/seed-techpass-support) with the TechPass and SEED support.

</details>

<details>
<summary>What should I do if I receive the error <b>Defender offboarding package has expired! Please download a new offboarding package from the docs portal</b> while running the offboarding package?</summary>

This error indicates that your offboarding package is outdated.

For detailed steps on offboarding your device, please refer to the appropriate guide:
- [Windows offboarding steps](offboard-device/windows)
- [macOS ofboarding steps](offfboard-device/mac-os)

Download the offboarding package from the provided page and complete the offboarding steps.

If you continue to experience the same or any other error, [raise a service request](https://go.gov.sg/seed-techpass-support) with the TechPass and SEED support.

</details>

<details>
<summary>What should I do if I encounter an error on my macOS device while running the offboarding package to remove SEED components like Cloudflare WARP, Microsoft Defender, or Tanium Client?</summary>

Try running the script again. If you still experience any error, [raise a service request](https://go.gov.sg/seed-techpass-support) with the TechPass and SEED support.

</details>

<details>
<summary>What should I do if I receive the error <b>Intune ID not found. Please manually input your Intune ID</b> after successfully completing Phase A to offboard my device from SEED components.</summary>

You may encounter this error if we are unable to auto-retrieve your Intune Device ID due to incorrect configurations on your device.

1. To get your Intune Device ID, either:
    - Go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) and retrieve the Intune Device ID from your account profile.
    - If you cannot access the TechPass portal, [raise a service request](https://go.gov.sg/seed-techpass-support) with the TechPass and SEED support to obtain your Intune Device ID.

2. Once you have your Intune Device ID, proceed with **Phase B: Submit Intune Device ID** to remove the device record.

If there is a significant time lapse between Phase B and Phase A, the latest version of the SEED components may be reinstalled on your device. In that case, you need to repeat **Phase A: Offboard device from SEED components**.

</details>

<details>
<summary>What should I do if I received an email stating that my offboarding was unsuccessful?</summary>

This can happen if you submitted an incorrect Intune Device ID.

1. To get your correct Intune Device ID, either:
    - Retrieve the Intune Device ID from your account profile on the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).
    - If you cannot access the TechPass portal, [raise a service request](https://go.gov.sg/seed-techpass-support) with the TechPass and SEED support to obtain the correct Intune Device ID.

2. Complete the offboarding steps for your device.

For detailed steps on offboarding your device, please refer to the appropriate guide:
- [Windows offboarding steps](offboard-device/windows)
- [macOS ofboarding steps](offfboard-device/mac-os)

If your offboarding is still unsuccessful despite submitting the correct Intune Device ID, please [raise a service request](https://go.gov.sg/seed-techpass-support).

</details>

<details>
<summary>What should I do if I did not receive the successfully offboarded email after submitting my Intune Device ID</summary>

It may take up to 30 minutes for the SEED team to send the successfully offboarded email to you. If you still have not received this email, please [raise a service request](https://go.gov.sg/seed-techpass-support).

If the TechPass and SEED support team completes the offboarding for you, you may not receive this email from the SEED team. However, the TechPass and SEED support team can confirm if you have successfully offboarded your device from SEED.

</details>

<details><summary>How do I offboard from Defender using Hive offboarding package if my Internet Device belongs to Hive organisation?</summary>



If your Defender organisation is Hive, contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to get the offboarding package and follow the below steps for your device:

<details><summary>macOS</summary>

1. Save the offboarding script to the **Downloads** folder.

    > **Note**:
    > Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, hive_mac_valid_until_2023-04-30.sh

2. Go to the **Terminal** and run the following command:
      ```
      sudo /bin/sh ~/Downloads/<name_of_offboarding_script.sh>
      ```
    >- **Note:**
    > The file name *name_of_offboarding_script* in this command is only an example. When you run the command, specify the file name of the offboarding script you downloaded.

3. Go back to the **Finder** icon in the **Dock**.

4. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.

5. Drag the app to the Bin, or select the app and choose **File** > **Move to Bin**.

</details>

<details><summary>Windows</summary>

1. Save the offboarding script in your **Downloads** folder.

  > **Note**:
  > Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *hive_windows_valid_until_2023-09-07.cmd*.

2. Go to **Start** and type **cmd**.
3. Right-click on **Command Prompt** and select **Run as administrator**.
4. If prompted, enter your Windows password.
5. Run the following commands:
     ```
     cd "%USERPROFILE%\Downloads\"

     .\<name_of_offboarding_script.cmd>
     ```
> **Note:**
> Name of the .cmd file mentioned in this command is only an example. When you run the command, specify the file name of the offboarding script you downloaded.  

</details>

</details>


