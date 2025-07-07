# Linux Mint 21.1 VM Installation (VirtualBox)

This README documents the steps to install Linux Mint 21.1 Cinnamon as a Virtual Machine (VM) using VirtualBox, with correct system settings.

---

## 🖥️ VirtualBox VM Installation

### Step 1: Create a New VM

* Open **Oracle VirtualBox**
* Name: `Linux Mint`
* Type: `Linux`
* Version: `Ubuntu (64-bit)`
* ISO: Browse to `linuxmint-21.1-cinnamon-64bit.iso`
* ✅ Optionally check **Skip Unattended Installation** (see explanation below)

> 🧠 **About "Skip Unattended Installation"**
>
> VirtualBox offers a feature called "Unattended Installation" to speed up the process by applying values you fill in during VM creation.
>
> * ✅ If you **check** Skip Unattended Installation → you'll be taken to Linux Mint’s full installation GUI and go through the steps manually.
> * ❌ If you **leave it unchecked**, VirtualBox will apply the settings you provided (username, password, hostname) and streamline the install.
>
> ⚠️ Regardless of which option you choose, you will still boot into the Linux Mint **Live Session**, where you must click **Install Linux Mint** to begin the actual OS installation.

---

### Step 2: Boot from ISO

After starting the VM, you will see a menu:

➡️ Select:

```
Start Linux Mint 21.1 Cinnamon 64-bit
```

This will launch the **Live Session** (試用模式，不是正式安裝)。

> 💡 Any change you make in Live Session (like installing software or changing settings) will be **lost after reboot**, unless you go through full installation.

---

### Step 3: Start Installation

Once you're in the Live Desktop:

🖱 Double-click the icon: **Install Linux Mint**

Follow the on-screen instructions:

1. Language & Keyboard: default is fine
2. Wi-Fi: optional (can skip)
3. Installation Type: select `Erase disk and install Linux Mint` (this only affects the VM disk)
4. Time zone: choose your location
5. Username and password: set as you like
6. Wait for installation to complete and reboot the VM

> 📝 If you skipped Unattended Installation, you will be asked to fill in user and system info here.

---

## ✅ Summary

* VM created and installed using official ISO (no USB required)
* Either manual or unattended installation paths are supported
* Installation starts from Live Session regardless of method

This setup can be used for labs, portfolio, or future deployments.
