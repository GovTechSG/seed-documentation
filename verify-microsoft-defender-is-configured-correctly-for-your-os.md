### Ensure Microsoft Defender is configured correctly for your OS

<br>
<details>
  <summary style="font-size:18px">macOS</summary>

  1. Open **Terminal** and run `mdatp health`.
  2. Take note of the value displayed for **org_id**.

  > **Note**:
  > If this command does not return anything, it indicates your device does not have Defender. Hence, [proceed to onboard your macOS device to SEED](onboard-device/mac-os).

  3. Identify the organisation corresponding to this **org_id** from the following table. This is the organisation of the Defender or the antivirus on your device.

    | org_id  | Organisation |
    | ------------- |:-------------:|
    | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
    | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
    | 6389e966-e334-461d-86ce-0fed12484620      | Hive    |

  4. Choose the required step from the following:

    - If your organisation id corresponds to WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and you can ignore the rest of this section.

    - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to get the offboarding package to unenrol your device. See the [offboarding FAQs](offboard-device/seed-offboarding-faqs.md) to know how to unenrol your device from Defender using the Hive offboarding package.
    
    - If your device is enrolled with a different MDM, contact your organisation IT support to unenrol your device from it.

Within the next few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can Sign in to Company Portal app, click the three dots and choose **Check status** to check for policy or profile updates. It may take a while to complete the synchronisation. When completed, the screen will show the timestamp of the last successful sync.


</details>

<details>
  <summary style="font-size:18px">Windows</summary>

1. Go to the **Start** menu and enter **Powershell**.
2. Right-click on the search result for **PowerShell** and select **Run as Administrator**

![open powershell](/images/offboarding-windows/run_powershell.png)

3. On **Powershell**, run the following command.

```
$reg64 = [Microsoft.Win32.RegistryKey]::OpenBaseKey([Microsoft.Win32.RegistryHive]::LocalMachine, [Microsoft.Win32.RegistryView]::Registry64)
$OrgID =  $reg64.OpenSubKey("SOFTWARE\MICROSOFT\Windows Advanced Threat Protection\Status").GetValue("OrgID")
echo $OrgID
```
4. Take note of the value displayed for **OrgID**.

![find-org-id](/images/offboarding-windows/org_id_win.png)

?> Note: If you don't get any response, it means you do not have Defender installed on your device. You can skip the steps in this section. Hence, [proceed to onboard your Windows device to SEED](onboard-device/windows).

5. Identify the organisation corresponding to this **OrgId** from the following table. This is the organisation of the Defender or the antivirus on your device.

  | OrgId  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
  | 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

6. Choose the required step from the following:

  - If your organisation id corresponds to WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and you can ignore the rest of this section.

  - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [Hive support](mailto:GDS_DEN@hive.gov.sg) to get the offboarding package to unenrol your device. See the [offboarding FAQs](offboard-device/seed-offboarding-faqs.md) to know how to unenrol your device from Defender using the Hive offboarding package.
    
  - If your device is enrolled with a different MDM, contact your organisation IT support to unenrol your device from it.

Within the next few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can manually sync by going to **Start** > **Settings** > **Accounts** > **Access work or school** > **Work or School Account** > **Info** > **Sync**. Alternatively, Open the Company Portal app on your device, go to **Settings** > **Sync**. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.


 <!--

 4. Based on the **org_id**, identify the organisation of the Defender or the antivirus on your device.
 
 > **Note**:
  >- The org_id displayed depends on the TechPass account used for enrolling your device to SEED.
  >- If your TechPass ID used for SEED onboarding is similar to <em>your_name<span>@</span>tech.gov.sg</em> or <em>your_name<span>@</span><agency>.gov.sg</em>, your device will be onboarded to SEED under WOG profile - SG Govt M365 profile.</li>
  >- If your TechPass ID used for SEED onboarding is similar to <em>your_name<span>@</span>techpass.gov.sg</em>, your device will be onboarded to SEED under TECHPASS profile.

  > **Note**: If you have any issues in accessing the link to download the offboarding script,
  >- Access the link in incognito mode.
  >- Make sure you are using only the [supported browsers](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/additional-resources/best-practices?id=supported-browsers).
  >- If you still have issues in downloading the script, create a [support request](https://go.gov.sg/seed-techpass-support).

  5. Once you get the offboarding script, run it on your device to unenrol Defender from your device completely.

   > **Note**:
   > For more information on how to run the offboarding script to remove Defender from the macOS device, refer to **[Remove existing software on your device](prerequisites-for-onboarding?id=remove-existing-software-on-your-device)**.

  


  windows
  The OrgId displayed depends on the TechPass account you used for enrolling your device to SEED.

  > **Note**:
  >- The org_id displayed depends on the TechPass account used for enrolling your device to SEED.
  >- If your TechPass ID used for SEED onboarding is similar to <em>your_name<span>@</span>tech.gov.sg</em> or <em>your_name<span>@</span><agency>.gov.sg</em>, your device will be onboarded to SEED under WOG profile - SG Govt M365 profile.</li>
  >- If your TechPass ID used for SEED onboarding is similar to <em>your_name<span>@</span>techpass.gov.sg</em>, your device will be onboarded to SEED under TECHPASS profile.


  > **Note**:
>- If you have any issues in accessing the link to download the offboarding script, try accessing the link in incognito mode or one of the [supported browsers](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/additional-resources/best-practices?id=supported-browsers).
>- If you still have issues in downloading the script, create a [support request](https://go.gov.sg/seed-techpass-support).

- For all other organisation ids, contact your organisation's MDM administrator or Defender administrator to get the respective offboarding script and proceed to step 7.

7. Once you get the offboarding script for your current MDM organisation, run it on your device to unenrol your device from it completely.
  -->
