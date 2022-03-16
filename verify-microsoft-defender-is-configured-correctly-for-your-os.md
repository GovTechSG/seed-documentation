# Verify Microsoft Defender is configured correctly for your OS

<details>
  <summary>macOS</summary>
<ol>
<li>Open <b>Terminal</b> and run <code>mdatp health</code>.</li>
<li>Verify if one of the following is displayed as the <b>org_id</b>:</li>
  <ul>
    <li>49237d71-42ac-425a-a803-881b92cc18ce</li>
    <li>faa36a5e-2da6-4225-8e27-226177c801a0</li>
  </ul>
<div class="warn">
Value <em>49237d71-42ac-425a-a803-881b92cc18ce</em> indicates that you are a TechPass tenant and value <em>faa36a5e-2da6-4225-8e27-226177c801a0</em> indicates that you are a WOG tenant.
</div>
<li>If your <b>org_id</b> matches one of them, it indicates that <b>Microsoft Defender</b> has been configured correctly and you may ignore the rest of this section.</li>
<li>If your <b>org_id</b> is different from the above two values, it means your device is still using with a different MDM and hence complete the following steps to unenrol your device from that MDM:</li>
  <ol type = "a">
    <li>Contact your organisation's MDM administrator or Defender ATP administrator to get respective offboarding script.</li>
    <div class="warn">
    If your <b>org_id</b> is <em>6389e966-e334-461d-86ce-0fed12484620</em>, it indicates that your device is still enrolled with Hive. Contact <a href="mailto:gds_den@tech.gov.sg">GDS team</a> to get the respective offboarding script.
    </div>
    <li>Run the offboarding script to unenrol your device from that MDM completely. For more information on how to run the offboarding script, refer to <b>step d. Remove Microsoft Defender for Endpoint</b> in <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-offboarding-instructions-for-macos">SEED offboarding guide for macOS users</a>. Now <b>Endpoint Manager</b> installs the <b>Microsoft Defender</b> client with the correct configurations within few hours. </li>
    </ol>

?> For more information on this, see [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned). At any time, users can open the Company Portal app, **Settings** > **Sync** to immediately check for policy or profile updates.

<li>Repeat steps 1-3 to confirm if <b>Microsoft Defender</b> is configured correctly now.</li>
</ol>
</details>

<details>
  <summary>Windows</summary>
<ol>
<li>In the search box on the taskbar, type <b>regedit</b>, then select <b>Registry Editor</b> from the results and run it as administrator.</li>
<li>In the <b>Registry Editor</b>, go to <b>Computer</b> > <b>HKEY_LOCAL_MACHINE</b> > <b>SOFTWARE</b> > <b>Microsoft</b> > <b>Windows Advanced Protection</b> > <b>Status</b>.
<li>Verify if one of the following is displayed as the <b>OrgId</b>:</li>
  <ul>
    <li>49237d71-42ac-425a-a803-881b92cc18ce</li>
    <li>faa36a5e-2da6-4225-8e27-226177c801a0</li>
  </ul>
<div class="warn">
Value <em>49237d71-42ac-425a-a803-881b92cc18ce</em> indicates that you are a TechPass tenant and value <em>faa36a5e-2da6-4225-8e27-226177c801a0</em> indicates that you are a WOG tenant.
</div>
<li>If your <b>OrgId</b> matches one of them, it indicates that <b>Microsoft Defender</b> has been configured correctly and you may ignore the rest of this section.</li>
<li>If your <b>OrgId</b> is different from the above two values, it means your device is still enrolled with a different MDM and hence complete the following steps to unenrol your device from that MDM:</li>
  <ol type = "a">
    <li>Contact your organisation's MDM administrator or Defender ATP administrator to get respective offboarding script.</li>
    <div class="warn">
    If your <b>OrgId</b> is <em>6389e966-e334-461d-86ce-0fed12484620</em>, it indicates that your device is still enrolled with Hive. Contact <a href="mailto:gds_den@tech.gov.sg">GDS team</a> to get the respective offboarding script.
    </div>
    <li>Run the offboarding script to unenrol your device from that MDM completely. For more information on how to run the offboarding script, refer to <b>step d. Remove Microsoft Defender for Endpoint</b> in <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-offboarding-instructions-for-windows">SEED offboarding guide for Windows users</a>. Now <b>Endpoint Manager</b> installs the <b>Microsoft Defender</b> client with the correct configurations within few hours. </li>
    </ol>

?> For more information on this, see [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned). At any time, users can open the Company Portal app, **Settings** > **Sync** to immediately check for policy or profile updates.

<li>Repeat steps 1-4 to confirm if <b>Microsoft Defender</b> is configured correctly now.</li>
</ol>
</details>
