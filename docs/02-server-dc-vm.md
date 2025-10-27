# Windows Server (Domain Controller) Lab Setup

- This part explains how I configured **Oracle VirtualBox** to create a Windows Server virtual machine (VM) that will serve as my **Domain Controller (Server-DC)**.  
  The goal is to build a safe, personal Active Directory lab — the same kind of setup used in real corporate IT environments.  
<br><br>
- Why do this? It’s the best way to learn **Active Directory**, **Group Policy**, and other help desk-level administration skills without risking a real network. You can break things, experiment, and rebuild as needed.  
<br><br>
- Eventually, I’ll add a second machine (like a Windows 10/11 client) and join it to the domain — but for now, this guide focuses on getting the **Server-DC** up and running.  

---

## 1. Install Oracle VirtualBox

1. Go to [virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads).  
2. Download the latest version of VirtualBox for your OS (Windows, macOS, or Linux).  
3. Run the installer **as Administrator** and accept the default settings — make sure the **networking features** are checked.  
4. Once installed, open **Oracle VM VirtualBox Manager**.  
5. (Optional) Download and install the **VirtualBox Extension Pack** from the same page.  
   - This enables extra functionality like USB 2.0/3.0 support and clipboard sharing.  

---

## 2. Download Windows Server ISO

1. Visit Microsoft’s official evaluation center:  
   👉 [https://www.microsoft.com/en-us/evalcenter/](https://www.microsoft.com/en-us/evalcenter/)  
2. Select **Windows Server 2019** or **Windows Server 2022**.  
3. Choose the **ISO** file option (not VHD).  
4. Fill out the short form and download the ISO (about 5–6GB).  
5. Save it somewhere easy to find, like your Desktop or Downloads folder — you’ll attach it later.

---

## 3. Create the Server-DC Virtual Machine

1. In VirtualBox, click **New**.  
2. Enter a name for the VM, such as:  
   > `Server-DC`  
3. Select the following:  
   - **Type:** Microsoft Windows  
   - **Version:** Windows Server 2019 (64-bit) or Windows Server 2022 (64-bit)  
4. Set **Memory (RAM)** to at least **4096 MB (4GB)**.  
5. Create a new virtual hard disk:  
   - **Type:** VDI (VirtualBox Disk Image)  
   - **Storage:** Dynamically allocated  
   - **Size:** 60GB or larger  
6. Click **Create** to finish the basic setup.

---

## 4. Attach the Windows Server ISO

1. Select your `Server-DC` VM → click **Settings** → **Storage**.  
2. Under *Controller: IDE*, click the **Empty** disk icon.  
3. On the right side, click the small disk button → **Choose a disk file...**  
4. Locate and select your downloaded **Windows Server ISO**.  
5. Click **OK** to save the configuration.  

---

## 5. Configure Networking

1. Open **Settings → Network**.  
2. For **Adapter 1**, set:  
   - **Attached to:** *Host-only Adapter* (this lets your client VM talk to your server).  
3. (Optional) Add **Adapter 2** set to *NAT* — this gives the server internet access if needed for updates.  
4. Click **OK** to confirm.  

> 💡 The Host-only adapter is like your internal lab network.  
> The NAT adapter connects to the outside internet (but isn’t required for local AD work).

---

## 6. Start the Server and Install Windows

1. Select the `Server-DC` VM and click **Start**.  
2. When the Windows Setup screen appears:  
   - Choose your language, time, and keyboard.  
   - Click **Install Now**.  
3. Choose **Windows Server 2019/2022 Standard (Desktop Experience)**.  
   - The *Desktop Experience* gives you a full GUI (important for beginners).  
4. Accept the license, select **Custom installation**, and install to the default disk.  
5. Wait for installation to finish — the VM will reboot automatically.  

---

## 7. Complete Initial Setup

1. When prompted, set a strong **Administrator password**.  
2. After login, you’ll land on the **Server Manager** dashboard — this opens automatically on every boot.  
3. From here, you can start adding **Roles and Features** like Active Directory Domain Services (AD DS).  

> 💡 Server Manager is your control panel for managing server roles, users, and features — it opens by default because Windows Server assumes you’re there to administer something.

---

## 8. Snapshot Your Clean Install (Highly Recommended)

Before you start configuring anything:  

1. In VirtualBox Manager, right-click your `Server-DC` VM → **Snapshots** → **Take Snapshot**.  
2. Name it something like **“Fresh Install - Before AD Setup”**.  

That way, if anything goes wrong later, you can easily roll back.

---

## 9. Summary

| Component | Purpose |
|------------|----------|
| **Oracle VirtualBox** | Virtualization platform to create your lab |
| **Windows Server VM (Server-DC)** | The heart of your lab — will run Active Directory and manage users |
| **Server Manager** | Opens automatically for role and feature management |
| **Host-only Adapter** | Simulates an internal company network for your test environment |
| **Snapshot** | Acts as a restore point before making major changes |

---

## Result

After setup, your **Server-DC VM** boots into Windows Server with **Server Manager** open and ready.  
You now have the foundation to install **Active Directory Domain Services (AD DS)** and create your own domain — the first big step toward mastering IT Help Desk and systems administration skills.
