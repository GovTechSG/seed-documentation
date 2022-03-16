# Raise an incident support request
If you experience any uninformed service interruption or degraded service, please raise a [SEED incident support request](https://form.gov.sg/6099efa30d6a0a0012dff367).

If you encounter any issues with Cloudflare WARP, Tanium, Defender ATP or Intune, please refer to the following instructions on how to collect diagnostic information to be included in the support request.

### Cloudflare Access Troubleshooting Information
Please include the diagnostics information from the Cloudflare Access Application Launcher for us to troubleshoot any issues with your connection.

1. Please login to the [Cloudflare Access Application Launcher](https://gccgovsg.cloudflareaccess.com)
2. Click on the menu on the top right and click Account.
3. Navigate to the Diagnostics section at the bottom of the page.
4. Click the "Click to copy" link.
5. Paste the information into a text file and attach it to the support request.

### Cloudflare WARP Diagnostic Logs

Please run the Cloudflare WARP diagnostics to collect diagnostic
information about your laptop and send it to us. We will use this
information and seek support from Cloudflare to diagnose any issues with
the WARP client.


For Windows users:

```cmd
C:\Program Files\Cloudflare\Cloudflare WARP\warp-diag.exe
```

For MacOS users:

```bash
/Applications/Cloudflare WARP.app/Contents/Resources/warp-diag
```

This will create a zip file on your Desktop containing all the logs and
diagnostic information captured by Cloudflare WARP.

Please attach the zip file to the support request.


### Collecting HAR Files

Please follow this guide to collect the HAR file when experiencing problems connecting to the GCC 2.0 CMP or SGTS service.

>? Please use Google Chrome or Microsoft Edge. Mozilla Firefox will need to be configured to trust your system's trusted root certificate store. Safari is not supported.

[Google Chrome](https://developer.chrome.com/docs/devtools/open/):
1. Command+Option+C (Mac) or Control+Shift+C (Windows, Linux, Chrome OS).
2. Click on Network
3. Enable Preserve Log
4. Try to login to the GCC 2.0 CMP or SGTS service through Cloudflare Access
5. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please note this in your support request.
6. Right click the log of network requests and click Save All as HAR with Content


[Mozilla Firefox](https://developer.mozilla.org/en-US/docs/Tools):
1. Ctrl + Shift + I or F12 on Windows and Linux, or Cmd + Opt + I on macOS.
2. Click on Network
3. Enable Persist Logs
4. Try to login to the GCC 2.0 CMP or SGTS service through Cloudflare Access
5. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please note this in your support request.
6. Right click the log of network requests and click Save All as HAR with Content


[Microsoft Edge](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/open/?tabs=cmd-Windows)
1. Press F12 or Control+Shift+I (Windows, Linux) or Command+Option+I (macOS).
2. Click on Network
3. Enable Preserve Log
4. Try to login to the GCC 2.0 CMP or SGTS service through Cloudflare Access
5. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please note this in your support request.
6. Right click the log of network requests and click Save All as HAR with Content

Once the HAR file is saved, please attach the HAR file to the support request.
