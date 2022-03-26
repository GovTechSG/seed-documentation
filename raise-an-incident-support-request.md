# Incident support request
Raise an [incident support request](https://form.gov.sg/6099efa30d6a0a0012dff367) if you experience:

- uninformed service interruption or degraded service.

- issues with Cloudflare WARP, Tanium, Defender ATP or Intune. Please attach the diagnostics information for [Cloudflare Access](#cloudflare-access-troubleshooting-information) and [Cloudflare WARP](#cloudflare-warp-diagnostic-logs) to this request for troubleshooting.

- connectivity issues while accessing GCC 2.0 CMP or SGTS services. Please [generate HAR file](#generate-har-file) to this request for troubleshooting.

### Cloudflare Access troubleshooting information
*To get Cloudflare Access Application Launcher diagnostics information*:  

1. Log in to [Cloudflare Access Application Launcher](https://gccgovsg.cloudflareaccess.com).
2. Click your profile name in the upper-right corner and choose **Account**.
3. Go to **Diagnostics** section and click **Click to copy**.
5. Paste the copied information to a text file and attach it to the support request.

### Cloudflare WARP diagnostic logs

*To get Cloudflare WARP diagnostics*:
1. Depending on your OS, run the provided command to get the Cloudflare WARP diagnostics.

<details>
  <summary>&nbsp;&nbsp;Windows</summary>

`C:\Program Files\Cloudflare\Cloudflare WARP\warp-diag.exe`

  </details>

 <details>
 <summary>&nbsp;&nbsp;macOS</summary>

 `/Applications/Cloudflare WARP.app/Contents/Resources/warp-diag`

 </details>

Logs and diagnostic information captured by Cloudflare WARP will be saved as a zip file on your Desktop.

2. Attach the zip file to the support request.


### Generate HAR file

This section provides the instructions to generate HAR file for the [supported browsers](best-practices) when you experience problems connecting to the GCC 2.0 CMP or SGTS services.

- [Google Chrome](#generate-har-file-for-google-chrome)

- [Mozilla Firefox](#generate-har-file-for-mozilla-firefox)

- [Microsoft Edge](#generate-har-file-for-microsoft-edge)

#### Generate HAR file for Google Chrome

1. Open Google Chrome and right-click anywhere and select **Inspect** or press Command+Option+C (Mac) or Control+Shift+C (Windows). The Developer tools panel will be displayed.
3. Go to **Network** and select **Preserve log**.
5. Log in to GCC 2.0 CMP or any SGTS service through Cloudflare Access.
5. Verify if a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
6. Right click on any item within the **Network** tab and click **Save All as HAR with content**.
7. Save the HAR file.

#### Generate HAR file for Mozilla Firefox

?> Make sure your Mozilla Firefox is configured to trust your system's trusted root certificate store.

1. Open Firefox and go to application menu > **More tools** > **Web Developer Tools** or press Ctrl+Shift+I (Windows) or Command+Option+I (macOS) and click **Network**. The Developer Tools will be displayed.
2. Click **Network Settings** in the upper-right of the Developer Tools panel and enable **Persist Logs**.
3. Log in to GCC 2.0 CMP or any SGTS service through Cloudflare Access.
4. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
6. Right click the log of network requests and choose **Save All as HAR**.
7. Save the HAR file.

#### Generate HAR file for Microsoft Edge

1. Open Microsoft Edge and go to application menu > **More tools** > **Developer tools** or or Control+Shift+I (Windows) or Command+Option+I (macOS). The Developer tools will be displayed.
2. Go to **Network** and select **Preserve log**.
4. Try to login to the GCC 2.0 CMP or SGTS service through Cloudflare Access
5. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
6. Right click the log of network requests and click **Save All as HAR with content**.
7. Save the HAR file.
