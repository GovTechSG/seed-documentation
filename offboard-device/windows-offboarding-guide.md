# Windows offboarding guide

 This guide provides instructions for you to offboard your Windows device onboarded to SEED.

## Audience

- Users who need to offboard their Windows device from SEED.

## Prerequisites

Before you begin, make sure you have the following:

- An active TechPass account
- A SEED onboarded device
- [Optional] Your Intune Device ID 

### Get Intune Device ID

You need your Intune Device ID during the offboarding process. Here is how to find it:

?> **Tip**<br>Click the triangle to view more details about each method.

<details>
<summary>Method 1: Retrieve Intune Device ID from your Windows device</summary>

1. Open **PowerShell** and run the following commands:

```
$rootKey = [Microsoft.Win32.RegistryKey]::OpenBaseKey(
 [Microsoft.Win32.RegistryHive]::LocalMachine,
 [Microsoft.Win32.RegistryView]::Registry64
)
$enrollmentsKey = $rootKey.OpenSubKey("Software\Microsoft\Enrollments")
$intune_id = "Intune ID not found"
foreach ($name in $enrollmentsKey.GetSubKeyNames()) {
 $enrollmentIdKey = $enrollmentsKey.OpenSubKey($name)
 if ($enrollmentIdKey.GetValue("ProviderID") -ieq "MS DM Server") {
     $intune_id = $enrollmentIdKey.OpenSubKey("DMClient\MS DM Server").GetValue("EntDMID", "Intune ID not found")
     break
 }
}
Write-Output $intune_id

```
2. Take note of the Intune Device ID that is displayed on the **Powershell** window.

</details>

<details>
<summary>Method 2: Retrieve Intune Device ID from TechPass portal</summary>

1. On your non-SE GSIB device, go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).
2. On the TechPass portal, at the top right, go to your user name and click **My Account**. Your **Profile** details are displayed.
3. Take note of the **Intune Device ID** from the **Profile** page.

    ![tp-intune-device-id](../images/offboarding-windows/tp-portal-intune-device-id.png)

</details>


<details>
<summary>Method 3: Raise a service request to retrieve Intune Device ID.</summary>

> **Note**: Use this method if you cannot log in to your GMD or TechPass portal.

- [Raise a service request](https://go.gov.sg/seed-techpass-support) to retrieve your Intune Device ID.

</details>

> **Note**:mFor more information, refer to [Offboarding FAQ](/faqs/offboarding-faq.md).


## Phase A: Offboard device from SEED components

1. Go to the **Start** menu and enter **Powershell**.
2. Right-click on the search result for **PowerShell** and select **Run as Administrator**

    ![open powershell](../images/offboarding-windows/run_powershell.png)

3. On **Powershell**, run the following command.

```
$reg64 = [Microsoft.Win32.RegistryKey]::OpenBaseKey([Microsoft.Win32.RegistryHive]::LocalMachine, [Microsoft.Win32.RegistryView]::Registry64)
$OrgID =  $reg64.OpenSubKey("SOFTWARE\MICROSOFT\Windows Advanced Threat Protection\Status").GetValue("OrgID")
echo $OrgID
```


4. Take note of the value displayed for **OrgID**.

    ![find-org-id](../images/offboarding-windows/org_id_win.png)

5. Refer to the following table and identify your **Defender organisation** and download the offboarding package.

  | OrgID | Defender organisation | Offboarding package |
  | ------------- |:-------------:|:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_wog_windows) |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    | [Download offboarding script](https://k3uwa66lu3tj6uxft46666ynhe0uvzor.lambda-url.ap-southeast-1.on.aws/local_tp_windows)    |
  | 6389e966-e334-461d-86ce-0fed12484620 | Hive | Contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to get the offboarding package. |

?> **Important**
>
> - If your **Defender organisation** is **Hive**, please disregard the remaining steps in this document. Instead, you should obtain the offboarding package from Hive support and unenroll your device from Defender. Refer to [Offboarding FAQ](/faqs/offboarding-faq.md) for guidance on unenrolling your device from Defender using the Hive offboarding package.
>   
> - If your **Defender organisation** is either **WOG** or **TechPass**, you should use your TechPass account to download the offboarding package and proceed with the remaining steps.
>   
> - If your **Defender organisation** is **none of the above**, please reach out to the IT support of the organization that provided you with the device for further assistance.



6. Go to the folder where you downloaded the ZIP file and extract the files. You should see the following two files.

    ![extract-files](../images/offboarding-windows/windows-extracted-files.png)

> **Note**: The file names vary with the organisation.

7. Right-click the unzipped folder to select **Show more options** > **Copy as path**. The folder path is now saved to your clipboard.

8. On **Powershell**, run the following command to go to the folder which has the extracted files:

    ```
    cd {Path from clipboard}
    ```

    For example:

    ```
    cd "C:\Users\testUser\Downloads\Offboarding_local_tp_windows"

    ```

    ![directory](../images/offboarding-windows/windows_cd_downloads.png)

10. To run the script, enter the following command:

    ```
    powershell.exe -ExecutionPolicy Bypass .\local_windows_offboarding.ps1

    ```

    When you see the following success message on your **Powershell**, you are automatically directed to the **SEED offboarding: Request to remove device record** form to submit the Intune Device ID.

    ![macos-success-message](../images/offboarding-windows/windows_success_message.png)

>**Note**: Ensure you complete the steps in Phase B immediately after Phase A. If not, your device update policy may reinstall the latest version of the deleted SEED components.

## Phase B: Submit Intune Device ID to remove device record

### Prerequisites

- Successful completion of [Phase A: Offboard device from SEED components](#phase-a-offboard-device-from-seed-components).
- **Intune Device ID**: Generally, when you successfully offboard your device from the SEED components, the Intune Device ID is automatically displayed on the **SEED Offboarding: Device Record Removal** form. If it is not displayed, see [Get Intune Device ID](#get-intune-device-id).
- [Optional] If you had submitted an incident request with the TechPass and SEED support team to offboard your device from the SEED components, please have the reference number ready as we may need this information.

### Submit Intune Device ID

**To submit Intune Device ID**:

1. Ensure your **Intune Device ID** is displayed on the form. If it is not displayed, provide it.
2. Enter your organisational email address in **Organisational Email Address** and click **Verify**.
3. Enter the OTP you receive at this email address.  
4. Indicate if you had any issues while completing **Phase A**.
5. [Optional] If you had issues completing **Phase A**, we encourage you to provide the **Support Ticket Number**.
6. Click **Submit**. When this request is processed successfully, we send a notification via email.

    ![successfully-offboarded-email](../images/offboarding-windows/win-successfully-offboarded-email.png)


> **Note**:
> - We require up to 30 minutes to process your server-side offboarding request.
>- If you are still waiting to receive an email after 30 minutes, please [raise a service request](https://go.gov.sg/seed-techpass-support).

## Device clean-up policy

The device clean-up policy applies to SEED users with TechPass IDs belonging to the TechPass Entra ID. You can identify a TechPass Entra ID account if your TechPass ID's domain is *techpass.gov.sg*. For example, *james_lee@techpass.gov.sg* is associated with the TechPass Entra ID.

The primary objective of this policy is to remove inactive device records from the Intune portal.

> **Note**:
> 
> - The device clean-up policy does **not apply** if your TechPass ID belongs to the **WOG Entra ID**.
> - A TechPass ID in the WOG Entra ID typically aligns with your organizational email address, which is in the format *\<your_name\>@\<acronym for your agency\>.gov.sg*. For example, *peter_wilson@tech.gov.sg*.


### What happens if my GMD is inactive?


If your TechPass ID belongs to the TechPass Entra ID and you have not logged into your GMD for 90 consecutive days, the GMD becomes inactive, and its records are soft deleted from the Intune portal.

It is essential to note that when your device records are soft deleted, it does not wipe or retire the device. Instead, the device record is temporarily removed from Intune.

As a result, SEED administrators will not be able to access details such as the device's health status, and they can no longer manage it from the SEED Dashboard.


### Restore my device records on Intune

You can restore your device records on Intune by simply logging in to your GMD device the next time, provided that:

- Your TechPass account is still active.
- Your MDM certificate is still valid or within 180 days after its expiry.

## MDM certificate

When you onboard your Internet Device to SEED, you receive an MDM certificate that is valid for one year from the date of onboarding. The certificate is automatically renewed if you are logged in to your GMD when it expires.

> **Note**: - Ensure that your TechPass account remains active.

If the MDM certificate expires, it can be automatically renewed by logging in to your device within 180 days from the expiration date. In such cases, re-onboarding your device to SEED is not required.

If the certificate remains expired for over 180 days, your device record is permanently deleted, preventing access to SGTS products.





