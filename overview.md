# SEED overview

This site provides information to help developers onboard securely to SEED or SEED+, manage their devices, and understand how government security requirements are enforced across engineering endpoints.

## What is SEED and SEED+?

- **SEED**  
  **Security Suite for Engineering Endpoint Devices (SEED)** is the Singapore Government's implementation of Identity and Access Management (IAM) and Zero Trust framework.  It aims to protect the Government's engineering resources, such as Government on Commercial Cloud (GCC) and the Singapore Government Tech Stack (SGTS), against unauthorised access.

Zero Trust replaces traditional Virtual Private Network (VPN) connections and network-based security policies with a standardised central identity provider. This enforces access policies, ensuring that only authorised users with devices compliant with device postures gain access.

- **[SEED+](/overview#what-is-seed+)**  
  SEED+ extends SEED to offshore development centres (ODCs) — developers working outside Singapore. It provides additional controls such as CyberArk, USB blocking, and always-on Cloudflare WARP.

> Not sure which one applies to you? Refer to the [Identify your onboarding persona](/onboard-device/identify-onboarding-persona.md) guide.

## Why do we need SEED?

![why-do-we-need-seed](images/why-do-we-need-seed.png)

- Detects and provides remediation steps for known malware.
- Verifies if the endpoint meets the required security hardening baseline based on the corresponding Centre of Internet Security (CIS) benchmark for the installed endpoint operating system.
- Detects if the endpoint’s operating system version and security patches are up to date.
- Prevents access to the resources of GCC and the SGTS services if the above requirements are not satisfied.

## How does SEED work?

![how-does-seed-work](images/how-does-seed-work.png)

SEED comprises three key components:

- TechPass
- Cloudflare
- SEED Dashboard

## What can SEED do on my device?

| SEED capabilities                            | Supported |
| ----------------------------------------------------------- | :-------: |
| View device information such as model number and OS version |     ✔️     |
| View the names of installed applications                 |     ✔️     |
| Identify your device by name                       |     ✔️     |
| Reset a lost or stolen device to factory settings          |     ✔️     |
| View browsing history                              |     ❌     |
| Access emails, contacts, and calendar                     |     ❌     |
| Access documents                                         |     ❌     |



## What is SEED+

**SEED+** extends SEED to provide additional security for offshore development centres (ODCs) — developers working outside Singapore on government projects.

### Who is SEED+ for

- Offshore developers on projects sponsored by Singapore Government agencies
- macOS or Windows devices
- Developers with an active TechPass account
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

- No admin rights on your device. All `sudo` or install-level actions require approval.
- Elevation requests will go to your project’s POC.
- Devices idle for more than 30 days may be offboarded automatically.

> SEED+ users follow the same onboarding steps as SEED vendors. Refer to the [Onboard as a vendor guide](/onboard-device/vendor).



























