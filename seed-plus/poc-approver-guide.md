# SEED+ POC Approver Guide

This guide is for Point-of-Contact (POC) approvers managing elevation requests submitted by offshore developers onboarded to SEED+. These requests are triggered when users attempt actions requiring elevated privileges on their devices (e.g. running `sudo` commands, installing software).

---

## How elevation requests work

When a SEED+ user performs a restricted action:
- CyberArk EPM will display a prompt.
- The user clicks **Activate** to submit a request with justification.
- POC approvers will receive an email notification and must review the request in the CyberArk EPM portal.

---

## Examples of typical elevation requests

These are common actions that trigger elevation prompts:

- `sudo htop` from macOS terminal  
  ![sudo htop request (macOS)](../images/seed-plus/poc-approval/sudo-htop-macos.png)

- Software installation on Windows  
  ![install software request (Windows)](../images/seed-plus/poc-approval/software-install-windows.png)

---

## Approving a Temporary Elevation Request

To approve a request from the CyberArk EPM portal:

1. Go to [CyberArk EPM portal](http://sg.epm.cyberark.com/SAML/GovTech)  
   ![Login screen](../images/seed-plus/poc-approval/login-screen.png)

2. Log in with your **TechPass credentials**  
   *Refer to the [TechPass user guide](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/get-invited-and-onboard-to-techpass) if you have not set this up.*

3. Navigate to **Events Management**  
   ![Access request list](../images/seed-plus/poc-approval/access-request-list.png)

4. Click **All filters**

5. Check the box **With justification**

6. Click **Apply**

7. You will see a list of pending requests. Look for the relevant request.  
   ![Request detail](../images/seed-plus/poc-approval/request-detail.png)

8. Click the **3-dot menu (···)** next to the request and select **Approve temporary elevation**  
   ![Approve button](../images/seed-plus/poc-approval/approve-button.png)

Once approved:
- A temporary elevation policy will be created automatically in the **Policies** section.  
  ![Policy created](../images/seed-plus/poc-approval/policy-created.png)
- This policy is valid for **24 hours**.
- Inform the user that elevation access has been granted.

---

## JIT (Just-In-Time) Access Elevation

This method is triggered **automatically every hour** when there are pending JIT access requests. Approvers must take action to create and confirm the JIT policy.

### Steps to handle JIT requests:

1. Open the email notification from CyberArk.  
   ![Sample email notification](../images/seed-plus/poc-approval/sample-jit-email.png)

2. Go to [CyberArk EPM portal](http://sg.epm.cyberark.com/SAML/GovTech) and log in using TechPass.

3. In the portal:
   - Navigate to **Events Management**
   - Click **All filters**
   - Check **With justification**
   - Click **Apply**  
     ![Filter for justification](../images/seed-plus/poc-approval/jit-filters.png)

4. Locate the request. A sample justification will be shown.  
   ![Sample justification](../images/seed-plus/poc-approval/jit-justification.png)

5. Click **Create JIT access and elevation policy**

6. On the policy page:
   - Under **Permissions (Local Groups)**, add:
     - `admin` for macOS
     - `Administrators` for Windows  
     ![JIT policy creation](../images/seed-plus/poc-approval/jit-policy.png)

7. Click **Create** and then **Confirm**

Once completed, the user will receive the temporary elevation automatically on their device.  
![User notification](../images/seed-plus/poc-approval/user-jit-notification.png)

---

## Notes

- JIT and Temporary Elevation are two different flows, but both require POC approval.
- If unsure whether to approve, consult your internal agency process or security team.
