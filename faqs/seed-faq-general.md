# General FAQ

<details><summary>What is TechPass and why do I need it?</summary>

  TechPass is an Identity & Access Management (IAM) and Single Sign-On (SSO) solution. It provides a seamless login experience while accessing tools across Singapore Government Technology Stack (SGTS) and allows to easily manage access control for the users from a centralised location. It is a prerequisite for onboarding your device(non-GSIB) to SEED. For more information, refer to [TechPass Documentation][techpass-documentation].

</details>
<hr />


<details><summary>What is SEED and why should I onboard my device to SEED?</summary>

Security Suite for Engineering Endpoint Devices (SEED) is a Mobile Device Management (MDM) solution. SEED ensures data security to protect the digital information of your organisation from unauthorised access, malicious users, and corruption. When you onboard a non-GSIB device to SEED, it becomes a GMD. It allows you to remotely manage access to highly sensitive data, provide user authentication, and can wipe off data from the device remotely if it is lost or compromised.

</details>
<hr />
<details><summary>I have lost my GMD. What should I do?</summary>

1. Inform the manager-in-charge and operations manager and get an approval to delete the data from the lost device.
2. Raise a [service request][service-request] to notify the SEED team about the lost device.
3. In this service request, indicate if the device had any sensitive data to prioritise the remote wipe.
4. Attach the approvals from your managers so that the SEED Administrator can take the required actions accordingly to prevent any data breach.

</details>
<hr />
<details><summary>What happens when the security of a GMD is compromised?</summary>

Once the SEED team detects that a security of the device is compromised, it will contact the device owner to disconnect the affected device from the network. SEED proceeds to do a remote wipe, after getting the required consent and approval from the device owner and the manager-in-charge, respectively.

</details>
<hr />
<details><summary>What happens when a remote wipe is performed on a GMD?</summary>

Remote wipe in SEED is the feature where SEED administrator can remotely delete and destroy data on a device or system. When remote wipe is performed on a device, all the data on it will be erased. For more information, refer to the [Terms and Policies][terms-and-policies].

</details>
<hr />
<details><summary>Is remote wipe done only on devices that belong to public sector agencies?</summary>

No, remote wipe will be done on any GMD device that is lost to prevent data breach. For more information, refer to the [Terms and Policies][terms-and-policies].

</details>
<hr />
<details><summary>I have already enrolled my device with Microsoft Intune under my organisation or with other MDM solution. Will this impact when I onboard my device to SEED?</summary>

Yes, this impacts your SEED onboarding. Before onboarding to SEED, remove your existing Microsoft Intune enrolment under your organisation's tenancy or other MDM solution on your device.

</details>
<hr />
<details><summary>What data is collected by Microsoft Intune?</summary>

To know about the data collected by Microsoft Intune, refer to [Data collection in Intune](https://docs.microsoft.com/en-us/mem/intune/protect/privacy-data-collect).

</details>
<hr />

[techpass-documentation]: https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/
[terms-and-policies]: https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/terms-and-policies
[service-request]: https://form.gov.sg/#!/6099efa30d6a0a0012dff367
