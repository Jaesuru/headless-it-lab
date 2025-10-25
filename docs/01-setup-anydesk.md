# AnyDesk Setup
<p>This part explains the first steps in this project on how I conigured **AnyDesk** to manage my headless Windows desktop completely remotely. All you have to do is turn the computer on, and use another computer (in my case, a MacBook air) to remote into it. 
<br><br>
Before we get started, this part is **optional**, but its fun little part that gets you familiarized with remote desktop configurations and using tools that are used in real-world environments. It also just saves space in my room, personally. 
<br><br>
And one more thing, the intended desktop that will be headless later on, will first have to have a method of display, so... grab a monitor, mouse, keyboard, and HDMI dummy header for these next few steps. You won't need them after though!</p>
---

## 1. Install AnyDesk
1. Download from [anydesk.com/download](https://anydesk.com/download).
2. Run the installer **as Administrator**.
3. During setup, select:
    > ✅ “Install AnyDesk for system startup (service mode)”
4. Once installed, note your device’s **AnyDesk ID** (I blurred mine out, for obvious reasons...)
<img width="882" height="471" alt="Screenshot 2025-10-24 at 8 53 15 PM" src="https://github.com/user-attachments/assets/415ab6e4-d6e0-47ff-9eb7-efd3844c5600" />

## 2. Enable Unattended Access
1. Open **Settings -> Security**.  
2. Check **Enable unattended access**.  
3. Set a strong password and also enable two-factor authentication if you want to be extra secure.  
4. Uncheck **Always show incoming requests** so you don’t need to accept connections manually.
<img width="891" height="619" alt="Screenshot 2025-10-24 at 8 57 49 PM" src="https://github.com/user-attachments/assets/65be2f52-bdec-4de7-a3b2-471c05e29741" />

## 3. Verify Service Mode
To make sure AnyDesk starts automatically:

1. Press `Win + R`, type `services.msc`, and press Enter.  
2. Find **AnyDesk Service** → confirm **Status: Running** and **Startup type: Automatic (Delayed Start)**.  
3. If needed, start the service manually once.

---

## 4. Test Remote Access
1. Restart the desktop.  
2. From another device, open AnyDesk and connect using the desktop’s ID.  
3. You should see the **login screen**, no need to accept manually.

If it doesn’t connect, ensure:
- The PC is online (check router device list or ping it).
- The AnyDesk service is running.
- The correct ID or alias is used.

---

## Notes
- Use **Ethernet** for reliable startup connections (Wi-Fi may connect too late).
- Add a **dummy HDMI adapter** so AnyDesk always renders a display.
- Consider enabling **“Automatic login”** if the system is purely for lab use.
- When turning on the desktop that you're going to remote into, give it a good minute or two, the service that starts AnyDesk usually takes a while. 

---

## Result
After setup, the desktop boots fully headless and connects to AnyDesk automatically, allowing remote control without peripherals or monitor.
