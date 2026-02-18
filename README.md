# 🛡️ Pi-hole + VPN Ready-to-Go

Welcome! This project effectively allows you to have an ad blocker for your entire home network and a VPN to access it from outside, all on a single Raspberry Pi.

🚫 **Goodbye Ads**: Browse faster and without distractions.
🔒 **VPN Included**: Connect to your home securely from your mobile device when you are away (4G/5G) without opening any ports.

---

## 📦 What do you need? (Materials)
1.  🍓 **Raspberry Pi 4** (or higher).
2.  💾 **MicroSD Card** (minimum 8GB).
3.  🔌 **Ethernet Cable**.
4.  ⚡ **USB-C Power Supply** for the Pi.

---

## 🚀 Installation Guide ("Step-by-Step")

### Step 1: Download and Flash 💾
1.  Download the **`invisix-distro.img`** file we generated.
2.  Download and install [**Raspberry Pi Imager**](https://www.raspberrypi.com/software/).
3.  Open the program:
    *   **Raspberry Pi Device**: Choose your model (Raspberry Pi 4).
    *   **Operating System**: Scroll to the bottom, choose "Use Custom" and select the `invisix-distro.img` file.
    *   **Storage**: Choose your SD card.
    *   **CLICK NEXT AND THEN "NO" TO EDIT SETTINGS**. (We have already configured them).
    *   Click **Write** and wait for it to finish.

### Step 2: Configure VPN (Magic!) ✨
*If you don't want VPN, skip this step.*

1.  Go to [**Tailscale.com**](https://tailscale.com) and create a free account (you can use Google/Microsoft).
2.  Go to **Settings > Keys**.
3.  **"Generate auth key"** button.
4.  Copy the long code starting with `tskey-...`.
5.  **On your computer**:
    *   Open the SD card you just flashed (it will appear as a disk named `bootfs`).
    *   Create a new text file named **`tailscale-auth.key`**.
    *   Paste your `tskey-...` key inside.
    *   Save and close.
6.  Eject the SD card.

### Step 3: Connect and Power On 🔌
1.  Insert the SD card into the Raspberry Pi.
2.  Connect the Internet cable (from Router to Pi).
3.  Connect the power cable.
4.  **Wait 5 minutes**. ⏳
    *   *The Pi will detect your network, auto-configure itself, and connect to the VPN.*

### Step 4: Configure your Router (The only manual step) ⚙️
For Pi-hole to work, your router needs to know it exists.

1.  Log in to your router's web interface (usually `http://192.168.1.1` or `http://192.168.0.1`).
2.  Find the **"DHCP"** or **"Local Network"** section.
3.  Find the list of connected devices and look for the one named `raspberrypi`.
4.  Enable the **"DHCP Reservation"** or **"Static Lease"** option for that device.
5.  Copy that IP (example: `192.168.1.50`).
6.  In the router's **DNS** configuration, set that IP (`192.168.1.50`) as the **Primary DNS**.

---

## ✅ Done!

### How do I use it?

**At Home (Wi-Fi):**
You don't have to do anything. Ads will disappear from your phones, tablets, and computers automatically.

**Away from Home (4G / Public Wi-Fi):**
1.  Install the **Tailscale** app on your phone.
2.  Log in with your account.
3.  Toggle the "Active" switch.
4.  Done! You are browsing securely through your home connection and without ads.

### Control Panel
To see how many ads you've blocked:
*   Web: `http://<YOUR-OBTAINED-IP>/admin`
*   Password: `admin`

---
*Made with ❤️ in Europe.*
