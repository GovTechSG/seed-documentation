# Announcements

### June 29, 2022

Newer version of Cloudflare WARP Client will be installed on your GMD on July 01, 2022 18:00 SGT:
- version 2022.5.342 for macOS
- version 2022.5.341 for Windows

The newer version of the Cloudflare WARP client will fix the memory leak issue observed on the older Cloudflare WARP clients.

**Customer Impact:**

During the client installation, your GMD will be disconnected from the SGTS resources you are accessing at that time. This installation may take up to five minutes.

Users whose GMD already has the newer version of the Cloudflare WARP client will not be impacted, and hence no action is required by them.

**Action Required:**

Ensure your GMD is connected to an active internet connection during the installation.

**Additional Information:**

If you can't access SGTS services after the newer client version is installed, please reboot your GMD. If the issue persists, please [raise an incident support request](raise-an-incident-support-request) with the respective SGTS service or products team.


### June 21, 2022

An issue has been identified with Cloudflare services on June 21 14:34 SGT. A fix has been implemented on Jun 21, 15:20 SGT and we are monitoring the outcome.

**Customer Impact:**

Users may have observed 500 errors while accessing the Internet and Cloudflare protected SGTS services using Cloudflare WARP.

While we monitor the fix, if you are still unable to access the Internet, please turn off WARP to access the Internet and raise an [incident support request](raise-an-incident-support-request) with the respective SGTS service or product team.

You may also visit the [Cloudflare status page](https://www.Cloudflarestatus.com/) for recent updates on this issue.
