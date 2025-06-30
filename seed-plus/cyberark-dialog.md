# CyberArk dialogs and permissions 

After your device is onboarded to SEED+, CyberArk Endpoint Privilege Manager (EPM) helps manage actions that require elevated permissions.

Some actions (like installing apps or running commands) may trigger dialogs. These are either:
- **Activate dialogs**: You can request permission. Your POC will approve or reject it.
- **Deactivate dialogs**: These are system-enforced. You cannot interact with them.

---

## Activate dialogs (require approval)

### 1. Application requires administrative privileges  
**Platforms**: Windows, macOS  
**Status**: Activate  
**What to do**: Click **Activate**. Enter justification if prompted. Request will be sent to your POC.  
![Windows](../images/epm/windows-admin-privileges.png)  
![macOS](../images/epm/macos-admin-privileges.png)

---

### 2. Application runs with administrative privileges  
**Platforms**: Windows, macOS  
**Status**: Activate  
**What to do**: Click **Activate**. Enter justification if prompted. Request will be sent to your POC.  
![Windows](../images/epm/windows-runs-admin.png)  
![macOS](../images/epm/macos-runs-admin.png)

---

### 3. Launch with elevated privileges  
**Platforms**: Windows only  
**Status**: Activate  
**What to do**: Click **Activate**. Enter justification if prompted. Request will be sent to your POC.  
![Windows](../images/epm/windows-launch-elevated.png)

---

### 4. Request administrative privileges  
**Platforms**: Windows only  
**Status**: Activate  
**What to do**: Click **Activate**. Enter justification if prompted. Request will be sent to your POC.  
![Windows](../images/epm/windows-request-admin.png)

---

### 5. Temporary permissions granted  
**Platforms**: Windows, macOS  
**Status**: Activate  
**What to do**: No action needed. You have been granted temporary admin access.  
![Windows](../images/epm/windows-temp-granted.png)  
![macOS](../images/epm/macos-temp-granted.png)

---

### 6. Temporary permissions expiration  
**Platforms**: Windows, macOS  
**Status**: Activate  
**What to do**: No action needed. This is an informational dialog to let you know access will expire.  
![Windows](../images/epm/windows-temp-expiring.png)  
![macOS](../images/epm/macos-temp-expiring.png)