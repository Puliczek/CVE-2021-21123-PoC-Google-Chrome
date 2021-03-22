# 📝 Description

**Google Chrome - File System Access API - vulnerabilities reported by Maciej Pulikowski**

**Total Bug Bounty Reward: $5.000**

This is Proof of Concept for:

* ***[Google Security_Severity]** CVE*
* **[HIGH]** [CVE-2021-21123](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21123)
* **[MEDIUM]** [CVE-2021-21129](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21129)
* **[MEDIUM]** [CVE-2021-21130](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21130)
* **[MEDIUM]** [CVE-2021-21131](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21131)
* **[MEDIUM]** [CVE-2021-21172](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21172)
* **[LOW]** [CVE-2021-21141](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21141)
  
The main security issue here is the operating system dialog "Save as" launched by Google Chrome, is showing to the user the wrong file extension of downloaded the file. It shows "Save as type: JPEG (.jpg)" but downloads virus.jpg.lnk that can download and run virus.exe by PowerShell. 

So it is a kind of spoofing extension of downloaded a file.

The bugs works in Google Chrome 86 and 87 on Windows, Mac, and Linux.
Of course, LNK works only on Windows, but we can change it to a different extension on Linux or Mac.

Google Blog posts:

* https://chromereleases.googleblog.com/2021/01/stable-channel-update-for-desktop_19.html
* https://chromereleases.googleblog.com/2021/03/stable-channel-update-for-desktop.html

Mentioned bugs are **"Reported by Maciej Pulikowski"**



# 📺 Youtube Proof of Concept

https://www.youtube.com/watch?v=l9swTtaRDNs

[![PoC Video](https://user-images.githubusercontent.com/12344862/111987402-7fcf6280-8b0f-11eb-8956-9868ac9a1866.png)](https://www.youtube.com/watch?v=l9swTtaRDNs)

**Thanks for the thumbs up 😀👍**

# 👨‍💻 Code PoC

**Requirements:** Nothing, you just need to run an HTML file in an older version of Google Chrome 86 or 87. If you want to test it with a .lnk file, you have to create FUD "lnkextra.lnk" file, because it is not included.


* **example_showSaveFilePicker.html** (The bugs works in Google Chrome 86 and 87. They are patched in 88+)

    CVE-2021-21123, CVE-2021-21129, CVE-2021-21130, CVE-2021-21131, CVE-2021-21141

    Playground of my examples for **showSaveFilePicker()**:
  * Save LNK file and show save as type: JPEG Image (*.jpg)
  * A many of whitespace and fake extensions in the description
  * RTL in description
  * Super long description
  * Many spaces in the extension
  * RTL in extension
  * Extension ends with space
  * Extension ends with a period
  * Save LNK file in a different way
  * EXTRA - Because everything happens in JS we can check if the user's browser is vulnerable

* **example_getFileHandle.html** (The bug works in Google Chrome 86, 87, and 88. It is patched in 89+)
  
  CVE-2021-21172 - **getFileHandle()** - Save .lnk file to selected folder 



# 💻 Useful links

- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)
- [File System Access - Documentation](https://wicg.github.io/file-system-access/)
- [File System Access Web API - Chromium Security Model](https://docs.google.com/document/d/1NJFd-EWdUlQ7wVzjqcgXewqC5nzv_qII4OvlDtK6SE8)
- [Chromium Source code - default download method blocking .lnk file](https://source.chromium.org/chromium/chromium/src/+/master:net/base/filename_util_internal.cc;drc=1c58af32060fa0ef3cfd4037fdc7913092d16ba2;l=155?q=%20EnsureSafeExtension&ss=chromium)

# 🤝 Show your support

**Give a ⭐️ if you liked the content**

# ✔️ Disclaimer
This project can only be used for educational purposes. Using this software against target systems without prior permission is illegal, and any damages from misuse of this software will not be the responsibility of the author.
