# General FAQ

<details><summary style="font-size:18px">What is TechPass and why do I need it?</summary>

  TechPass is an Identity & Access Management (IAM) and Single Sign-On (SSO) solution. It provides a seamless login experience while accessing tools across Singapore Government Technology Stack (SGTS) and allows to easily manage access control for the users from a centralised location. It is a prerequisite for onboarding your device(non-GSIB) to SEED. For more information, refer to [TechPass Documentation][techpass-documentation].

<hr /></details><br>

<details><summary style="font-size:18px">What is SEED and why should I onboard my device to SEED?</summary>

Security Suite for Engineering Endpoint Devices (SEED) is a Mobile Device Management (MDM) solution. SEED ensures data security to protect the digital information of your organisation from unauthorised access, malicious users, and corruption. When you onboard a non-GSIB device to SEED, it becomes a GMD. It allows you to remotely manage access to highly sensitive data, provide user authentication, and can wipe off data from the device remotely if it is lost or compromised.

<hr /></details><br>
<details><summary style="font-size:18px">I have lost my GMD. What should I do?</summary>

1. Inform the manager-in-charge and operations manager and get an approval to delete the data from the lost device.
2. Raise a [service request][service-request] to notify the SEED team about the lost device.
3. In this service request, indicate if the device had any sensitive data to prioritise the remote wipe.
4. Attach the approvals from your managers so that the SEED Administrator can take the required actions accordingly to prevent any data breach.

<hr /></details><br>
<details><summary style="font-size:18px">What happens when the security of a GMD is compromised?</summary>

Once the SEED team detects that a security of the device is compromised, it will contact the device owner to disconnect the affected device from the network. SEED proceeds to do a remote wipe, after getting the required consent and approval from the device owner and the manager-in-charge, respectively.

<hr /></details><br>
<details><summary style="font-size:18px">What happens when a remote wipe is performed on a GMD?</summary>

Remote wipe in SEED is the feature where SEED administrator can remotely delete and destroy data on a device or system. When remote wipe is performed on a device, all the data on it will be erased. For more information, refer to the [Terms and Policies][terms-and-policies].

<hr /></details><br>
<details><summary style="font-size:18px">Is remote wipe done only on devices that belong to public sector agencies?</summary>

No, remote wipe will be done on any GMD device that is lost to prevent data breach. For more information, refer to the [Terms and Policies][terms-and-policies].

<hr /></details><br>
<details><summary style="font-size:18px">I have already enrolled my device with Microsoft Intune under my organisation or with other MDM solution. Will this impact when I onboard my device to SEED?</summary>

Yes, this impacts your SEED onboarding. Before onboarding to SEED, remove your existing Microsoft Intune enrolment under your organisation's tenancy or other MDM solution on your device.

<hr /></details><br>
<details><summary style="font-size:18px">What data is collected by Microsoft Intune?</summary>

To know about the data collected by Microsoft Intune, refer to [Data collection in Intune](https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect).

<hr /></details><br>
<details>
<summary style="font-size:18px">I am unable to connect to AWS VPN client on port 443? </summary>

This is a known issue with Microsoft Defender version 101.54.16. To resolve this, install Microsoft Defender version 101.56.35 or later.

<hr /></details><br>
<details><summary style="font-size:18px">Why am I prompted to turn on my system integrity protection on my macOS device?</summary>

  This is a policy requirement of the SEED team. System Integrity Protection is a security technology in OS X El Capitan and later that's designed to help prevent potentially malicious software from modifying protected files and folders on your macOS. System Integrity Protection restricts the root user account and limits the actions that the root user can perform on protected parts of the macOS.

 <hr /></details><br>

 <details>
   <summary style="font-size:18px">What is the minimum version of macOS needed for onboarding it into Microsoft Intune?</summary>

 Big Sur 11 is the minimum version needed for a successful onboarding. If your macOS is an earlier version, ensure to [upgrade it to a later macOS version](https://support.apple.com/downloads/macos).

 > **Note**:
 > When you upgrade the OS of your Mac device, the OpenSSH settings found in `/etc/ssh/sshd_config` file may be reset. Hence, before proceeding to upgrade the OS of your Mac device, back up the `sshd_config` file so that you can easily restore if it gets reset during the OS upgrade.

 <hr /></details><br>

 <details>
   <summary style="font-size:18px">Why am I prompted to turn on File Vault encryption?</summary>

 File Vault encryption is needed to ensure device security and compliance.

 <hr /></details><br>

 <details><summary style="font-size:18px">Why does my device slowdown after onboarding to Microsoft Intune?</summary>

 SEED is designed to use **Microsoft Defender for Endpoint** to ensure device is free from malware, prevent and respond to advanced threats. If there is any other antivirus or anti-malware running simultaneously, it could compromise the performance of the operating system. To resolve this, disable or uninstall antivirus other than **Microsoft Defender for Endpoint**.

 <hr /></details><br>

 <details><summary style="font-size:18px">When I onboard my Mac device to SEED, why does it take up more than 100 GB of storage space?</summary>

The current `audit_control` configuration set by SEED could be the reason causing the audit logs to be written excessively to the `/private/var/audit` folder.

The latest configuration change for audit logs retention is 60 days and  5 GB.

If your `/private/var/audit` folder size is more than 5 GB, run the following commands to sync with the new policy.

```
audit -s
audit -e
```

 <hr /></details><br>




[techpass-documentation]: https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/
[terms-and-policies]: https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/additional-resources/terms-and-policies
[service-request]: https://form.gov.sg/#!/6099efa30d6a0a0012dff367
