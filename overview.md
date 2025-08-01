# SEED overview

SEED and SEED+ are security solutions for managing and protecting engineering endpoint devices used in government projects. This page explains what SEED and SEED+ are, how they work, and what users can expect during and after onboarding.

---

## SEED vs SEED+: At a glance

|  Feature | **SEED** | **SEED+** |
|---|---|---|
| Who it is for | Users working in Singapore on government engineering systems | Users working outside Singapore for government projects. <br><br> **Note**: SEED+ applies to users from fully qualified offshore development centres (ODCs) or those approved by their POC. New users will receive an email invitation to onboard to SEED, then proceed with SEED+ onboarding. Both new SEED+ users and existing users can refer to the [SEED+ section of this documentation](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices-seed/overview?id=what-is-seed+) for more details. |
| Device types | macOS and Windows | macOS and Windows |
| Admin rights  | Retained by user | Removed (CyberArk used for elevation) |
| USB storage blocking | No       | Yes (storage only) |
| Network access | No Always-On Cloudflare WARP | Always-on Cloudflare WARP |
| DNS configuration | No Preset DNS | Preset Cloudflare DNS (1.1.1.1, 1.0.0.1) |
| Onboarding flow | [Standard SEED onboarding](/onboard-device/identify-onboarding-persona.md) | [Standard SEED onboarding](/onboard-device/identify-onboarding-persona.md)|

> **Know which one applies to you?**  
> - [Go to SEED → What is SEED](#what-is-seed)  
> - [Go to SEED+ → What is SEED+](#what-is-seed+)

---

## What is SEED

**Security Suite for Engineering Endpoint Devices (SEED)** is the Singapore Government's implementation of Identity and Access Management (IAM) and Zero Trust framework. It aims to protect the Government's engineering resources, such as Government on Commercial Cloud (GCC) and the Singapore Government Tech Stack (SGTS), against unauthorised access.

Zero Trust replaces traditional Virtual Private Network (VPN) connections and network-based security policies with a standardised central identity provider. This enforces access policies, ensuring that only authorised users with devices compliant with device postures gain access.

---

## Why do we need SEED?

![why-do-we-need-seed](images/why-do-we-need-seed.png)

- Detects and provides remediation steps for known malware.
- Verifies if the endpoint meets the required security hardening baseline based on the corresponding Centre of Internet Security (CIS) benchmark for the installed endpoint operating system.
- Detects if the endpoint’s operating system version and security patches are up to date.
- Prevents access to the resources of GCC and the SGTS services if the above requirements are not satisfied.

---

## How does SEED work?

![how-does-seed-work](images/how-does-seed-work.png)

SEED comprises three key components:

- TechPass
- Cloudflare
- SEED Dashboard

---

## What can SEED do on my device?

| SEED capabilities                            | Supported |
|----------------------------------------------|:---------:|
| View device information such as model number and OS version | ✔️ |
| View the names of installed applications     | ✔️ |
| Identify your device by name                 | ✔️ |
| Reset a lost or stolen device to factory settings | ✔️ |
| View browsing history                        | ❌ |
| Access emails, contacts, and calendar        | ❌ |
| Access documents                             | ❌ |


### Next steps for SEED users

If SEED applies to you, you can proceed directly with onboarding.  
Go to the **Onboard to SEED** section in the sidebar.


## What is SEED+

**SEED+** extends SEED to provide additional security for offshore development centres (ODCs) — users working outside Singapore on government projects.

### Who is SEED+ for

SEED+ is intended for:

- Users working outside Singapore on projects sponsored by Singapore Government agencies
- macOS or Windows devices
- Users with an active TechPass account
- Users onboarded with POC approval

> A POC (point-of-contact) is a designated officer from the sponsoring agency who is responsible for approving your onboarding and access requests.



### What SEED+ includes

SEED+ uses the same baseline protection as SEED, with additional controls for offshore use:

- **CyberArk Endpoint Privilege Manager (EPM)**  
  Removes administrative rights and requires POC approval for elevated access.

- **USB storage blocking**  
  Blocks storage devices only. Peripherals like mouse and keyboard are allowed.

- **Cloudflare WARP**  
  Always stays on and connected.

- **DNS IP address preset**  
  Cloudflare DNS: `1.1.1.1` and `1.0.0.1`


### What to expect

- You will not have superuser access. All `sudo` or install-level actions must be approved via elevation requests.
- Elevation requests will be routed to your POC for approval.
- Devices that are idle for more than 30 days may be offboarded automatically.


### Next steps for SEED+ users

If SEED+ applies to you, follow the [Onboard as a vendor guide](/onboard-device/vendor) to begin.

After onboarding, go to the **SEED+ section** in the sidebar to learn more about:

- [CyberArk dialogs and permissions (Users)](/seed-plus/cyberark-dialog.md)  
- [Approval guide (POC)](/seed-plus/poc-approver-guide.md)


























