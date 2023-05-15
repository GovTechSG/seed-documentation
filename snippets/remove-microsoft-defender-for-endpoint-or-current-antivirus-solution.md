## Remove Microsoft Defender for Endpoint or current antivirus solution

1. Open **Terminal** and run `mdatp health`.
2. Note down the value displayed for **org_id**.
3. Identify the organisation corresponding to this **org_id** from the following table. This is the organisation of the Defender or the antivirus on your device.

  | org_id  | Organisation |
  | ------------- |:-------------:|
  | faa36a5e-2da6-4225-8e27-226177c801a0      | WOG     |
  | 49237d71-42ac-425a-a803-881b92cc18ce  | TechPass    |
  | 6389e966-e334-461d-86ce-0fed12484620      | Hive     |

  > **Note**:
  > If your organisation id(org_id) is not listed in this table, contact your organisation administrator to remove the antivirus solution from your device.
  > If your organisation id(org_id) is different from the above three, contact the respective MDM administrator to get the offboarding script.

4. Based on the organisation, download the SEED offboarding script from the following:

  | Organisation  | SEED offboarding script |
  | ------------- |:-------------:|
  | WOG      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/wog_mac)    |
  | TechPass      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/tp_mac)     |
  | Hive      | [Download offboarding script](https://26mucnez5qtouxu6dtg7bwcpwa0glupx.lambda-url.ap-southeast-1.on.aws/hive_mac)     |


  5. When prompted to log in, log in with your TechPass.

  > **Note**:
  >- If you have any issues in accessing the link to download the offboarding script, try accessing the link in incognito mode or one of the [supported browsers](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/additional-resources/best-practices?id=supported-browsers).
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

</details>
