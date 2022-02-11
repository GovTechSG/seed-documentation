# Frequently asked questions

<br>
<details>
  <summary>1. While onboarding my macOS to Intune, I don’t see any profiles. What should I do?</summary>
  <ol>
    <li>Make sure that you have signed in to the <strong>Company Portal</strong> app and see if profiles are listed. If you still do not see any profiles listed, go to step 2.</li>
    <li>Create another local user account and sign in to the <strong>Company Portal</strong> app.</li>
    <li>Repeat the process to setup Intune on your device.</li>
  </ol>  
  </details>
  <hr />
  <details>
  <summary>2. While onboarding to Intune, I get an error message, <em>"Could not download the identity profile from the Encrypted Profile Service. The credentials within the Device Enrolment profile may have expired."</em></summary>

  One of the possible reasons could be that your device was earlier onboarded by another user in Intune and was not offboarded properly.  

  To confirm if that is the case, contact the [SEED team](mailto:gcc2.0_support@tech.gov.sg)  with your device serial number. The SEED team can verify if your device was previously enrolled in Intune under a different user. If this is confirmed, offboard it properly before proceeding to onboard again.

  </details>
  <hr />

  <details>
    <summary>
    3. What is the minimum version of macOS needed for onboarding it into Microsoft Intune?
    </summary>

  Catalina 10.12.x is the minimum version needed for a successful onboarding. If your macOS is an earlier version, ensure to [upgrade it to a later macOS version](https://support.apple.com/downloads/macos).

  </details>
  <hr />

  <details>
    <summary>
  4. Why am I prompted to turn on File Vault encryption? </summary>

  File Vault encryption is needed to ensure device security and compliance.
  </details>
  <hr />
  <details>
  <summary>
  5. Why does my device slowdown after onboarding to Intune?</summary>

This could be due to two antiviruses running simultaneously. Disable one of them to see if it improves the performance of your device.

  </details>
  <hr />

  <details>
  <summary>
  6. While enrolling my device to SEED, I get an error message, "<em>Couldn’t add your device. Wait a few minutes, then try again or contact your company support.</em>" What should I do?
  </summary>

  As suggested wait for few minutes, retry enrolling your device to Intune and click <strong>Approve</strong> in the management profile.
  </details>
  <hr />

  <details>
  <summary>
  7. While approving the management profiles, I get a message "<em>Profiles cannot be approved while using remote or automated input method.</em>” What should I do?
  </summary>

  [Upgrade your macOS to the latest version](https://support.apple.com/downloads/macos) and ensure there is enough disk space available on your Mac device before retrying.
  </details>
  <hr />

<details>
  <summary>
  8. Why am I prompted to turn on my system integrity protection?
  </summary>

  It is a policy requirement by the SEED team. System Integrity Protection is a security technology in OS X El Capitan and later that's designed to help prevent potentially malicious software from modifying protected files and folders on your macOS. System Integrity Protection restricts the root user account and limits the actions that the root user can perform on protected parts of the macOS.

 </details><hr />
<details>
 <summary>
 9. I get an error message, “<em>You can’t use this version of the application <strong>Company Portal</strong> with this version of OS X.</em>" What should I do?</summary>

 [Upgrade to a later macOS version](https://support.apple.com/downloads/macos) and try again.
 </details>
 <hr />
 <details>
  <summary>
  10. Tanium client returns a 400 Bad Request Error when contacted by the Cloudflare Access landing page via localhost. What should I do now? </summary>

  This is due to the time synchronisation issue between Cloudflare and Tanium client. To fix this, resync the local time of your macOS or Windows machine.

  To check and sync your device time with the internet time server:
  <details><summary><strong>For macOS device</strong></summary>
  <ol>
   <li>From the <strong>Apple</strong> menu, select <strong>System Preferences</strong>.</li>

   <li>Go to <strong>Date & Time</strong>.</li>

   <li>Click the <strong>Lock</strong> icon.</li>

   <li>Select <strong>Set date and time automatically</strong> checkbox.  If you’d like to use a custom network time server, enter the domain name of the server.</li>
  </ol>
  </details>
  <details><summary><strong>For Windows 10 device</strong></summary>
  <ol>
  <li>Open the <strong>Start</strong> menu and click <strong>Settings</strong>. </li>
  <li>Choose <strong>Time & Language</strong>.</li>
  <li>Turn on <strong>Set time automatically</strong>.</li>
  <li>Click <strong>Sync now</strong> to synchronize with the time server.</li>

  <li>If you’d like to use a custom network time server, click <strong>Date, time & regional formatting</strong> from <strong>Related Settings</strong> at the upper-right corner. The <strong>Region</strong> settings page is displayed.</li>

  <li>Click <strong>Additional date, time & regional settings</strong> from Related settings</strong> at the upper-right corner. The Clock and Region settings page is displayed. </li>

  <li>Click <strong>Date and Time</strong>.</li>

  <li>Go to <strong>Internet Time</strong> tab and click <strong>Change settings</strong>.</li>

  <li>Enter the domain name of the server.</li>
  </ol>
  </details>
