# What is SEED+

Security Suite for Engineering Endpoint Devices (SEED) is the Singapore Government’s implementation of identity and access management (IAM) and zero trust security.

SEED+ extends SEED to provide additional security for offshore development centres (ODCs) — developers working outside Singapore on government projects.

---

## Who SEED+ is for

SEED+ is intended for:

- Offshore developers on projects sponsored by Singapore Government agencies
- macOS or Windows devices
- Developers with an active TechPass account
- Users onboarded with POC approval

> A POC (point-of-contact) is a designated officer from the sponsoring agency who is responsible for approving your onboarding and access requests.

---

## What SEED+ includes

SEED+ uses the same baseline protection as SEED, with additional controls for offshore use:

- **CyberArk Endpoint Privilege Manager (EPM)**  
  - Removes administrative rights on your account  
  - Elevation requests require approval from the POC  

- **USB storage blocking**  
  - Only applies to storage devices  
  - Mouse and keyboard USBs are not blocked  

- **Cloudflare WARP**  
  - Always stays on and connected  

- **DNS IP address preset**  
  - Uses Cloudflare DNS: `1.1.1.1` and `1.0.0.1`

---

## What to expect

- You will not have superuser access. Commands requiring `sudo` or installation privileges must go through an elevation request.

- Requests will be routed to your project’s POC, who will approve or reject them.

- If your device is idle for more than 30 days, it may be offboarded. Keeping the device online will prevent this.


## Getting started

The onboarding process for SEED+ follows the same steps as SEED vendor onboarding.

Refer to the [Onboard as a vendor](/onboard-device/vendor) guide to get started.

Your POC must approve your access before you can proceed.