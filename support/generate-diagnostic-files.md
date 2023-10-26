# Generate diagnostic files for raising a service request

This guide provides step-by-step instructions on generating and uploading diagnostic files for raising a service request. If you are experiencing connectivity issues while accessing GCC 2.0 CMP or SGTS services and require assistance, follow the steps below to troubleshoot common issues.

- To troubleshoot issues related to Cloudflare WARP, Tanium, Defender, or Intune, you should attach diagnostic files for Cloudflare Access and Cloudflare WARP to your service request.

- If you are facing connectivity problems with GCC 2.0 CMP or SGTS services, you should generate a HAR (HTTP Archive) file and attach it to your service request.


## Generate Cloudflare Access Diagnostic file

1. Log in to the [Cloudflare Access Application Launcher](https://gccgovsg.cloudflareaccess.com).
2. Click on your profile name in the upper-right corner and select **Account**.
3. Navigate to the **Diagnostics** section and click **Click to copy**.
4. Paste the copied information into a text file and attach it to your support request.

## Generate Cloudflare WARP diagnostic logs

1. Depending on your operating system, run the provided command to obtain the Cloudflare WARP diagnostics.

<details>
  <summary style="font-size:18px">&nbsp;&nbsp;Windows</summary>

  ```
  C:\Program Files\Cloudflare\Cloudflare WARP\warp-diag.exe

  ```

  </details>

 <details>
 <summary style="font-size:18px">&nbsp;&nbsp;macOS</summary>

 ```
/Applications/Cloudflare\ WARP.app/Contents/Resources/warp-diag

```

</details>

The logs and diagnostic information captured by Cloudflare WARP will be saved as a zip file on your Desktop.

2. Attach the zip file to the support request.


## Generate HAR file

This section provides instructions for generating a HAR (HTTP Archive) file for the supported web browsers when you encounter connectivity problems with GCC 2.0 CMP or SGTS products.


- [Google Chrome](#generate-har-file-for-google-chrome)

- [Mozilla Firefox](#generate-har-file-for-mozilla-firefox)

- [Microsoft Edge](#generate-har-file-for-microsoft-edge)

### Generate HAR file for Google Chrome

1. Open Google Chrome and right-click anywhere, then select **Inspect** or press Command+Option+C (macOS) or Control+Shift+C (Windows) to open the Developer Tools panel.
2. Go to the **Network** tab and enable **Preserve log**.
3. Log in to the [GCC 2.0 CMP](https://cmp.gcc.gov.sg/) or access the SGTS service through Cloudflare Access.
4. Verify if a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
5. Right-click on any item within the **Network** tab and select **Save All as HAR with content**.
6. Save the HAR file.

### Generate HAR file for Mozilla Firefox

?> **Note**: Make sure your Mozilla Firefox is configured to trust your system's trusted root certificate store.

2. Click on **Network Settings** in the upper-right corner of the Developer Tools panel and enable **Persist Logs**.
3. Log in to the [GCC 2.0 CMP](https://cmp.gcc.gov.sg/) or access the SGTS service through Cloudflare Access.
4. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
5. Right-click on the log of network requests and choose **Save All as HAR**.
6. Save the HAR file.

### Generate HAR file for Microsoft Edge

1. Open Microsoft Edge and go to the application menu > **More tools** > **Developer tools**, or press Control+Shift+I (Windows) or Command+Option+I (macOS) to open the Developer Tools.
2. Go to the **Network** tab and enable **Preserve log**.
3. Attempt to log in to the [GCC 2.0 CMP](https://cmp.gcc.gov.sg/) or access the SGTS service through Cloudflare Access.
4. Verify that a request was made to 127.0.0.1/zero_trust/auth with a 200 ok response. If not, please specify this in your support request.
5. Right-click on the log of network requests and click **Save All as HAR with content**.
6. Save the HAR file.