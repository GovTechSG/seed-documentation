# General FAQ

<details><summary style="font-size:20px;font-weight:bold">What is TechPass and why do I need it?</summary>

  TechPass is an Identity & Access Management (IAM) and Single Sign-On (SSO) solution. It provides a seamless login experience while accessing tools across Singapore Government Technology Stack (SGTS) and allows to easily manage access control for the users from a centralised location. It is a prerequisite for onboarding your device(internet) to SEED. For more information, refer to [TechPass Documentation][techpass-documentation].

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">What is SEED and why should I onboard my device to SEED?</summary>

Security Suite for Engineering Endpoint Devices (SEED) is a Mobile Device Management (MDM) solution. SEED ensures data security to protect the digital information of your organisation from unauthorised access, malicious users, and corruption. When you onboard an internet device to SEED, it becomes a GMD. It allows you to remotely manage access to highly sensitive data, provide user authentication, and can wipe off data from the device remotely if it is lost or compromised.

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">My TechPass account is active but my SEED onboarding email invitation has expired. How do I get another SEED onboarding email invitation?</summary>

Your SEED onboarding email invitation is valid for 30 days. If you have not onboarded to SEED following your TechPass onboarding within this 30 days, your invitation will no longer be valid.

If you use a non-SE GSIB device and if your TechPass account is active, to request for SEED:

1. Go to the [TechPass portal](http://portal.techpass.gov.sg) from your non-SE GSIB device.
2. Log in with TechPass.
3. Hover over your user name and click **My Account**.
4. In the **Profile** page, click **Request for SEED**.
5. You will receive the SEED onboarding invitation email within the next three business days.

Complete to onboard your internet (which is not a GSIB) device by following the instructions on [SEED documentation](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/prerequisites-for-onboarding).  

If you do not use a non-SE GSIB device and if your TechPass account is active, [create a service request with TechPass](https://go.gov.sg/techpass-sr) to receive the SEED onboarding invitation email again.

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">I have lost my GMD. What should I do?</summary>

1. Inform the manager-in-charge and operations manager and get an approval to delete the data from the lost device.
2. Raise a [service request][service-request] to notify the SEED team about the lost device.
3. In this service request, indicate if the device had any sensitive data to prioritise the remote wipe.

> **Note**: To wipe the device, the device needs to be powered on and be connected to the internet so it can receive the communication for it to be wiped.

4. Attach the approvals from your managers so that the SEED Administrator can take the required actions accordingly to prevent any data breach.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">What happens when the security of a GMD is compromised?</summary>

Once the SEED team detects that a security of the device is compromised, it will contact the device owner to disconnect the affected device from the network. SEED proceeds to do a remote wipe, after getting the required consent and approval from the device owner and the manager-in-charge, respectively.

> **Note**: To wipe the device, the device needs to be powered on and be connected to the internet so it can receive the communication for it to be wiped.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">What happens when a remote wipe is performed on a GMD?</summary>

Remote wipe in SEED is the feature where SEED administrator can remotely delete and destroy data on a device or system. Remote wipe is performed only if the device is stolen, lost or its security is compromised.

When remote wipe is performed on a device, all the data on it will be erased. For more information, refer to the [Terms and Policies][terms-and-policies].

> **Note**: To wipe the device, the device needs to be powered on and be connected to the internet so it can receive the communication for it to be wiped.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">Is remote wipe done only on devices that belong to public sector agencies?</summary>

No, remote wipe will be done on any GMD which is lost or whose security is compromised to prevent data breach. However, remote wipe is performed only if the device is stolen, lost or its security is compromised. For more information, refer to the [Terms and Policies][terms-and-policies].

> **Note**: To wipe the device, the device needs to be powered on and be connected to the internet so it can receive the communication for it to be wiped.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">I have already enrolled my device with Microsoft Intune under my organisation or with other MDM solution. Will this impact when I onboard my device to SEED?</summary>

Yes, this impacts your SEED onboarding. Before onboarding to SEED, remove your existing Microsoft Intune enrolment under your organisation's tenancy or other MDM solution on your device.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">What data is collected by Microsoft Intune?</summary>

To know about the data collected by Microsoft Intune, refer to [Data collection in Intune](https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect).

</details><hr />
<details>
<summary style="font-size:20px;font-weight:bold">I am unable to connect to AWS VPN client on port 443? </summary>

This is a known issue with Microsoft Defender version 101.54.16. To resolve this, install Microsoft Defender version 101.56.35 or later.

</details><hr />
<details><summary style="font-size:20px;font-weight:bold">Why am I prompted to turn on my system integrity protection on my macOS device?</summary>

  This is a policy requirement of the SEED team. System Integrity Protection is a security technology in OS X El Capitan and later that's designed to help prevent potentially malicious software from modifying protected files and folders on your macOS. System Integrity Protection restricts the root user account and limits the actions that the root user can perform on protected parts of the macOS.

 </details><hr />

 <details>
   <summary style="font-size:20px;font-weight:bold">What is the minimum version of macOS needed for onboarding it into Microsoft Intune?</summary>

 Big Sur 11 is the minimum version needed for a successful onboarding. If your macOS is an earlier version, ensure to [upgrade it to a later macOS version](https://support.apple.com/downloads/macos).

 <!--
 > **Note**:
 > When you upgrade the OS of your Mac device, the OpenSSH settings found in `/etc/ssh/sshd_config` file may be reset. Hence, before proceeding to upgrade the OS of your Mac device, back up the `sshd_config` file so that you can easily restore if it gets reset during the OS upgrade.
 -->

 </details><hr />

 <details>
   <summary style="font-size:20px;font-weight:bold">Can I upgrade my macOS to macOS 13 (Ventura)?</summary>

  You can now upgrade your Mac device to macOS 13(Ventura) and onboard it to SEED.


 </details><hr />

 <details>
   <summary style="font-size:20px;font-weight:bold">Why am I prompted to turn on File Vault encryption?</summary>

 File Vault encryption is needed to ensure device security and compliance.

 </details><hr />

 <details><summary style="font-size:20px;font-weight:bold">Why does my device slowdown after onboarding to Microsoft Intune?</summary>

 SEED is designed to use **Microsoft Defender for Endpoint** to ensure device is free from malware, prevent and respond to advanced threats. If there is any other antivirus or anti-malware running simultaneously, it could compromise the performance of the operating system. To resolve this, disable or uninstall antivirus other than **Microsoft Defender for Endpoint**.

 </details><hr />

 <details><summary style="font-size:20px;font-weight:bold">When I onboard my Mac device to SEED, why does it take up more than 100 GB of storage space?</summary>

The current `audit_control` configuration set by SEED could be the reason causing the audit logs to be written excessively to the `/private/var/audit` folder.

The latest configuration change for audit logs retention is 60 days and  5 GB.

If your `/private/var/audit` folder size is more than 5 GB, run the following commands to sync with the new audit log retention policy.

```
audit -s
audit -e
```

 </details><hr />

 <details><summary style="font-size:20px;font-weight:bold">Previously I had successfully onboarded my internet device to SEED, but now I received an email stating that I may not be able to access SEED-protected resources such as SGTS services and products. What’s the reason, and what should I do?</summary>

**Reason**: Most likely, this indicates that we detected some issues with your device configuration for SEED. For example, your Microsoft Defender could be unhealthy. As such issues pose a security risk, we revoke your access to SEED resources.

In this situation, the **action required** by you may vary based on your need:

- **Access automatically restored**: No action required. Your access is automatically restored if you shortly receive an email that you are successfully onboarded to SEED.

- **Restore my access to SEED-protected resources**:  Raise a [service request][service-request] and specify that your SEED access revoked due to device misconfiguration. This would allow us to process the ticket accordingly. Once your device configuration is remediated, we will send you the successfully onboarded email again, indicating you can now access SEED-protected resources again.
 
- **I no longer need to access SEED-protected resources**: [Offboard your device](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/offboard-device/offboard-device-from-seed) completely.

 </details><hr />

<details><summary style="font-size:20px;font-weight:bold">Why did I receive the successfully onboarded email even though I had received it before when I first onboarded my device to SEED?</summary>

If you've received this email again, some or all the services that make your device SEED-compliant may have had misconfiguration issues, causing you to temporarily lose access to SEED-protected resources .

When the configurations of the impacted services return to a healthy state, you will receive the successfully onboarded email indicating that you can access the SEED-protected resources again.

</details><hr />


[techpass-documentation]: https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/
[terms-and-policies]: https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/additional-resources/terms-and-policies
[service-request]: https://go.gov.sg/techpass-sr
