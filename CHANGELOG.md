## OpenIntuneBaseline Changelog

### v1.2
**Date: 20/09/2022**
</br>
* Another full re-export. 
* Removed object GUIDs for ease of maintenance moving forward.
* Prefixed all policies with "Baseline - Win - " to add some level of management naming convention.
* Did a pass of the CIS L1 Chrome and Edge policies and made some amendments.
* **New Policies**:

   - **Device Auditing** - Added after a review of in-built Intune security baseline settings.
   - **Microsoft Edge - Password Management (Device)** - Split from Edge Security policy to make per-tenant choices for what to do about Password Management. In my view, something is better than nothing, and in the absense of a corporate password manager, having users be suggested strong passwords and them being tied to their corporate account is a good thing.
   - **Windows Update for Business Configuration** - Added "AllowWUfBCloudProcessing" to the Windows Update Notifications policy and renamed.
   - **MS Store and Accounts (User)** - One of the policies was blocking MS Store apps from updating at the device level. Needs to be allowed at device level and blocked at user level (still only works for Ent/Edu, not Pro)
   - **Search** - Added after a review of in-built Intune security baseline settings.
   - **Skip User Enrollment Status Page** - It's widely understood the User ESP is mostly useless. Turns it off.

* **Amended Policies**:

   - **Google Chrome - Security (Device)** - Added many (but not all) CIS L1 settings. Note: Heavily locks down Chrome to restrict possible data exfil by logging into personal Google accounts. Disables a bunch of functionality in an attempt to encourage use of Edge as corporate browser.
   - **Microsoft Edge - Security (Device)** - Split out above Password Manager settings. Added many (but not all) CIS L1 settings. I don't necessarily agree with them all, and I'd much rather allow importing of other data (to encourage/enable a move from Chrome) but on a freshly built Autopilot device this is not so much of an issue. Forces user login using corp credentials. Limits the use of additional Profiles.
   - **Microsoft Edge - User Experience & Extensions (User)** - Removed most allowed extensions as they were mainly as an example. Left all but one.
   - **MS Store and Accounts (Device)** - As above.

* **Removed Policies**:

   - **Office - Update Settings (Device)** - Deemed unnecessary if utilising Servicing Profiles via config.office.com.
   - **Windows Update Notifications** - Bundled into above WUfB Configuration policy.

### v1.1 
**Date: 01/09/2022**
</br>
* Total re-export with a few minor changes to policies.
* Started a changelog to document changes better moving forward (sorry)

### v1.0 
**Date: 21/07/2022**
</br>
* Initial baseline upload.


