# ISO Verification – Linux Mint 21.1 Cinnamon

This document outlines the process to verify the **integrity** and **authenticity** of the Linux Mint 21.1 Cinnamon ISO using SHA256 checksum and GPG signature.

---

## 📥 Step 1: Download ISO and checksum files

Visit the official Linux Mint website:  
👉 https://linuxmint.com/edition.php?id=302

Download the following files:

- `linuxmint-21.1-cinnamon-64bit.iso`
- `sha256sum.txt`
- `sha256sum.txt.gpg`

Place all files in the same directory, e.g.:
C:\Users\YourName\Downloads\LinuxMint


---

## 🧪 Step 2: Verify SHA256 checksum (Integrity Check)

Open **PowerShell** in the folder where the `.iso` file is located and run:

```powershell
CertUtil -hashfile .\linuxmint-21.1-cinnamon-64bit.iso SHA256
```

⚠️ Be sure to include .\ before the file name, or the system may not find it.

📷 See integrity_check.png for example output.

---

## 🧪 Step 3: Compare with the official checksum

Compare the hash result with the corresponding line in sha256sum.txt.

Example result from PowerShell:

2df322f030d8ff4633360930a92d78829d10e515d2f6975b9bdfd1c0de769aca

Use the following command to search the file:

```powershell
findstr "2df322f030d8ff4633360930a92d78829d10e515d2f6975b9bdfd1c0de769aca" .\sha256sum.txt
```

This command helps you find string from the file.

✅ If the result is found in the .txt file, the ISO file is intact and has not been modified.
---

🧠 Summary
SHA256 checksum ensures the file was not corrupted or tampered with during the download.
Matching the hash confirms the ISO file is identical to the official release.

---

## 🔐 Step 4: Verify authenticity using GPG signature (Optional but Recommended)

Refer to the [Linux Mint forum guide](https://forums.linuxmint.com/viewtopic.php?f=42&t=291093)
👉"How to verify the ISO image on Windows – Authenticity Check" section.

📦 Prerequisite: Install Gpg4win

GPG is not pre-installed on Windows.

Download and install Gpg4win:
👉 https://gpg4win.org/download.html

Once installed, open PowerShell and run:
```
gpg --keyserver hkps://keyserver.ubuntu.com:443 --recv-key 27DEB15644C6B3CF3BD7D291300F846BA25BAE09
```

Then verify the signature:
```
gpg --verify sha256sum.txt.gpg sha256sum.txt
```

✅ If you see a message like:

"Good signature from "Linux Mint ISO Signing Key <root@linuxmint.com>"

it means the file is authentic and signed by the official maintainer.

📷 See authenticity_check.png for example output.

---

🧠 Summary
- SHA256 checks file integrity
- GPG signature check confirms authenticity (official origin)

This double verification ensures the ISO is both safe to use and genuinely released by Linux Mint.