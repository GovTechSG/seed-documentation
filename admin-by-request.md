# Admin By Request (ABR) – User guide

## Overview

**Admin By Request (ABR)** is a privilege management tool that allows users to request temporary local administrator rights in a controlled, auditable, and secure way.

It helps reduce risks from malware, accidental system changes, and unauthorised software installation, while still allowing users to perform legitimate admin tasks.

ABR works together with the following controls:

- **Platform SSO** – Revokes permanent local admin rights
- **Admin By Request (ABR)** – Handles day-to-day admin elevation requests, unless access is pre-approved
- **Cloudflare Always-On** – Enforces secure, always-on network connectivity

> ⚠️ **Pilot notice**  
> Admin By Request (ABR) is currently in a pilot phase.
>
> - This implementation applies only to selected users  
> - Not all users will have Admin By Request enabled  
> - Platform SSO and admin elevation workflows described in this guide apply only to pilot users  
> - Users not in the pilot group will not see Admin By Request prompts or functionality  

## Pre-requisites

Before using Admin By Request, ensure the following requirements are met.

### Platform SSO

Platform SSO must be configured on your device before Admin By Request can be installed automatically and function correctly.

Refer to the Platform SSO setup guide.

### Full Disk Access

Turn on **Full Disk Access** in **Privacy & Security** for the following:

- **Admin By Request System Extension**
- **Admin By Request**

![Full Disk Access settings for Admin By Request](images/abr-full-disk-access.png)

### Login Items & Extensions

Allow **Admin By Request ApS** under **Login Items & Extensions**.

![Login Items and Extensions for Admin By Request](images/abr-login-items.png)

### Endpoint Security Extensions

Allow the extension under:

**Login Items & Extensions** → **Extensions** → **By Category** → **Endpoint Security Extensions**

Select **Admin By Request.app**.

![Endpoint Security Extensions for Admin By Request](images/abr-endpoint-security-extension.png)

### Ensure ABR is working correctly

1. Select the **Admin By Request** icon in the menu bar.
2. Select **About Admin By Request**.
3. Confirm that the following statuses are **OK**:
   - **Operational Status**
   - **Cloud Connectivity**

If an error is shown, follow the steps in **What if Admin By Request is showing error?**.

![Admin By Request status screen](images/abr-about-status.png)

### Cloudflare Always-On

Ensure **Cloudflare Always-On** is enabled and connected before requesting admin access.

## User workflow

### Requesting admin access

1. Right-click the application you want to run, or double-click the `.pkg` file.
2. The **Admin By Request** prompt appears.

> **Note**  
> On Windows devices, right-click the application and select **Run as administrator**.


3. Enter the following details:
   - **Phone number**
   - **Email address**
   - **Reason for the request**  
     (The reason must be more than 5 characters.)
4. Complete MFA using your **tech.gov.sg** account.

![Admin By Request request prompt](images/abr-request-prompt.png)


### Approval process (if required)

#### Approval required mode

1. Your request is sent to ABR portal approvers.
2. The approver receives a notification by email or via the dashboard.
3. Once approved, a temporary admin session is granted.
4. Complete MFA using your **TechPass** account.

#### Pre-approved mode

If you are in pre-approved mode, your request is automatically approved.

### Elevated admin session

1. Select the **Admin By Request** icon in the menu bar.
2. Select **Request administrator access**.
3. Enter:
   - **Phone number**
   - **Email address**
   - **Reason for the request**
4. Complete MFA using your **tech.gov.sg** account.

When approved:

- A timer starts counting down the allowed admin duration.
- An ABR icon with the remaining time appears in the menu bar.
- Temporary local administrator rights are granted.

![Elevated admin session timer](images/abr-elevated-session.png)

#### What you can do during an admin session

- Install software
- Update applications
- Run scripts or tools that require admin rights

#### What you cannot do

- Disable Admin By Request
- Extend the session beyond the policy limit
- Gain permanent administrator rights

### MFA flows

#### MFA flow 1

![MFA flow step 1](images/abr-session-flow-1.png)

#### MFA flow 2

![MFA flow step 2](images/abr-session-flow-2.png)

### Approval screens

#### Approved screen 1

![Approval successful screen](images/abr-approved-1.png)

#### Approved screen 2

![Admin session started screen](images/abr-approved-2.png)

### Ending the session

The admin session ends when:

- The 15-minute timer expires, or
- You select **Finish** from the Admin By Request menu

After the session ends:

- Temporary admin rights are removed
- All elevated actions are logged in the ABR portal

![Admin session ending](images/abr-session-ending.png)


#### End session action

![End admin session](images/abr-end-session.png)

## Uninstall

Uninstallation requires a PIN.

Please approach the **SEED team** for assistance.

![Admin By Request uninstall screen](images/abr-uninstall.png)

## FAQ

<details>
<summary><strong>Is this permanent admin access?</strong></summary>

No. Admin By Request only grants temporary, audited administrator rights.  
Admin access is removed automatically when the session ends.
</details>

<details>
<summary><strong>Does Admin By Request work offline?</strong></summary>

No. Admin By Request requires an active internet connection because MFA must be completed online.
</details>

<details>
<summary><strong>Can users bypass Admin By Request?</strong></summary>

No. Users cannot bypass Admin By Request if device permissions and allowed applications are configured correctly.
</details>

<details>
<summary><strong>Can admins review what was done during an admin session?</strong></summary>

Yes. Administrators can review elevated activities via the Audit Log, if command logging is enabled.
</details>

<details>
<summary><strong>What if Admin By Request is showing error?</strong></summary>

If **Cloud Connectivity** is shown as **Red** and **Active Directory Domain** is empty, Admin By Request is unable to communicate with Entra ID.

![Admin By Request error status](images/abr-error-status.png)

Check the following:

- **Company Portal.app** for device registration errors
- **Device Management Profile** in macOS Settings  
  Ensure that **ABR-FDA** and **ABR-System-Extension** profiles exist

If there is an Intune enrolment issue, required profiles may not be pushed to the device.

![Intune profiles for Admin By Request](images/abr-intune-profiles.png)
</details>
