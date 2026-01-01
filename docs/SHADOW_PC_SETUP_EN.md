# BotW BetterVR Setup Guide for Shadow PC with Virtual Desktop

This guide explains how to set up and play BotW BetterVR on **Shadow PC** using **Virtual Desktop** to stream VR to your Meta Quest (or other compatible) headset.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [System Requirements](#system-requirements)
3. [Installation on Shadow PC](#installation-on-shadow-pc)
4. [Virtual Desktop Configuration](#virtual-desktop-configuration)
5. [Performance Optimization](#performance-optimization)
6. [Troubleshooting](#troubleshooting)

---

## Prerequisites

### Required Hardware
- **Shadow PC** (active subscription with dedicated GPU)
- **VR Headset** compatible with Virtual Desktop (Meta Quest, Quest 2, Quest 3, Quest Pro, etc.)
- **Internet Connection**: 
  - Minimum 30 Mbps download speed
  - Recommended: 50+ Mbps with latency < 30ms
- **Wi-Fi Router**: Wi-Fi 5 (802.11ac) minimum, Wi-Fi 6 recommended for VR headset
- **Ethernet connection** for Shadow PC (highly recommended)

### Required Software
- **Virtual Desktop** (paid app on Quest Store ~$20)
- **Virtual Desktop Streamer** (free PC application)
- **Cemu 2.6 or newer**
- **BotW BetterVR** (latest version)
- A legal copy of **The Legend of Zelda: Breath of the Wild** for Wii U

---

## System Requirements

### Shadow PC - Recommended Configurations

Shadow offers different service tiers. Here are the recommendations for BotW BetterVR:

#### ✅ Shadow Power Upgrade (RECOMMENDED)
- **GPU**: NVIDIA GTX 1080 / RTX equivalent or better
- **CPU**: Intel Xeon or equivalent (high single-thread performance)
- **RAM**: 12-16 GB
- **Expected result**: Smooth experience at 72-90 FPS in VR

#### ⚠️ Shadow PC Base
- **GPU**: NVIDIA GTX 1080 equivalent
- **CPU**: Variable performance
- **RAM**: 12 GB
- **Expected result**: Playable experience but may require graphical compromises

#### ❌ Shadow PC Boost (Minimum Configuration)
- May work with reduced graphical settings
- FPS limited to 60-72 FPS
- Not recommended for optimal VR experience

### Intel Integrated Graphics (i7 13th Generation)

**Short answer: Not recommended for VR**

Intel integrated graphics (Intel Iris Xe Graphics) on 13th generation i7 processors:

❌ **Are NOT recommended** for BotW BetterVR because:
- **Insufficient performance**: Intel iGPUs cannot maintain 60+ FPS in VR with Cemu
- **No robust Vulkan support**: Limited compatibility with the Vulkan API used by BetterVR
- **High latency**: VR requires very low render times that iGPUs cannot guarantee
- **VR streaming impossible**: Virtual Desktop requires a dedicated GPU to encode the VR stream

**Recommended alternative:**
- Use **Shadow PC** which provides a dedicated GPU in the cloud
- Or invest in a PC with dedicated GPU (NVIDIA GTX 1660 minimum, RTX 3060 recommended)

### Optimal Network Configuration

To minimize latency in VR streaming:

1. **Shadow PC → Internet**
   - Wired connection (Ethernet) highly recommended
   - Latency to Shadow: < 20ms ideal, < 30ms acceptable

2. **VR Headset → Router**
   - 5 GHz Wi-Fi (802.11ac) minimum
   - Wi-Fi 6 (802.11ax) recommended
   - VR headset should be close to router (same room preferably)

3. **Connection Test**
   ```
   Recommended total latency: < 40ms
   Ideal latency: < 25ms
   ```

---

## Installation on Shadow PC

### Step 1: Access Shadow PC

1. Launch your Shadow application on your local PC or phone
2. Connect to your Shadow PC
3. Once connected, you're now working on your cloud PC

### Step 2: Install Cemu

1. Download **Cemu 2.6 or newer** from [cemu.info](https://cemu.info/)
2. Extract Cemu to a folder (e.g., `C:\Games\Cemu`)
3. Configure Cemu following [this guide](https://cemu.cfw.guide/)
4. **IMPORTANT**: Test that BotW runs properly at 60+ FPS **before** installing the VR mod
   - Launch the game normally
   - Verify you get stable 60 FPS
   - If not, adjust graphical settings

### Step 3: Configure Cemu for Good Performance

1. Open Cemu → `Options` → `General Settings` → `Graphics` tab
2. Configure:
   - **Graphics API**: Vulkan (REQUIRED)
   - **Device**: Select your NVIDIA GPU
   - **VSync**: OFF (disabled)

3. Close Cemu completely

### Step 4: Install BotW BetterVR

1. Download the latest version of BotW BetterVR from [Releases](https://github.com/Crementif/BotW-BetterVR/releases)
2. Extract **ALL files** from the .zip into the folder where `Cemu.exe` is located
   - You should see: `.dll`, `.json`, and several `.bat` files next to `Cemu.exe`
3. DO NOT launch Cemu yet

### Step 5: Install Virtual Desktop Streamer

1. On Shadow PC, download **Virtual Desktop Streamer** from [https://www.vrdesktop.net/](https://www.vrdesktop.net/)
2. Install the application
3. Launch Virtual Desktop Streamer
4. Log in with the **same Oculus/Meta account** as your headset
5. Configure:
   - **Codec**: H.264 or HEVC (test both)
   - **Bitrate**: Automatic or 100 Mbps to start
   - **Resolution**: Automatic
   - Enable **"Use hardware encoding"**

---

## Virtual Desktop Configuration

### On the Quest Headset

1. Install **Virtual Desktop** from the Quest Store (purchase required ~$20)
2. Launch Virtual Desktop on your headset
3. The app should automatically detect your Shadow PC (make sure Virtual Desktop Streamer is running)
4. Select your Shadow PC and connect

### Optimal VR Settings in Virtual Desktop

Once connected to Shadow PC via Virtual Desktop:

1. Open the Virtual Desktop menu (left menu button)
2. Go to **Streaming**
   - **Video codec**: H.264+ (or HEVC if supported and excellent connection)
   - **Refresh rate**: 72 Hz or 90 Hz (depending on your headset)
   - **Bitrate**: 100-150 Mbps (adjust according to your connection)
   - **Slice mode**: Automatic
   - **SSW**: Disabled for native VR
   - **Resolution**: High or Automatic

3. Go to **Environment**
   - Choose any environment (you'll be in the game anyway)

### Launch BotW BetterVR

1. In Virtual Desktop, you see your Shadow PC desktop
2. On Shadow PC, double-click **`BetterVR LAUNCH CEMU IN VR.bat`**
   - This launches Cemu and automatically installs the BetterVR graphic pack
3. In Cemu, go to `Options` → `Graphic packs` → `The Legend of Zelda: Breath of the Wild`
4. **Enable the following graphic packs**:
   - ✅ **BetterVR** (required)
   - ✅ **FPS++** (required, otherwise crash)
   - ✅ Click **"Download Community Graphic Packs"** to update
5. Configure recommended graphical settings:
   - **Graphics**: 1440p or 1800p (no ultrawide), Anti-aliasing: Nvidia FXAA
   - **FPS++**: FPS limit to 120 or 144
   - **Enhancements**: Anisotropic filtering 16x
6. Close settings and launch the game from the Cemu game list
7. **Put on your VR headset** - the game should now be in VR! 🎮

---

## Performance Optimization

### If You Have Slowdowns (FPS < 60)

1. **Reduce resolution in Graphic Packs**
   - Go from 1800p to 1440p or 1080p
   
2. **Adjust Virtual Desktop**
   - Reduce bitrate to 80-100 Mbps
   - Switch to 72 Hz instead of 90 Hz
   
3. **Cemu Settings**
   - Disable high-resolution shadows
   - Reduce draw distance
   
4. **Close Shadow PC background applications**
   - Only Cemu and Virtual Desktop Streamer should be running

### To Improve Visual Quality

If you have stable FPS > 90:

1. Increase resolution to 1800p or 2160p
2. Enable additional graphical enhancements
3. Increase Virtual Desktop bitrate to 150-200 Mbps

### Reduce Latency

- **Use an Ethernet connection** for your local PC if you're controlling Shadow from there
- **Move your headset closer to the Wi-Fi router**
- **Close all downloads/streaming** on your network
- Check latency in the Virtual Desktop overlay (should be < 40ms total)

---

## Troubleshooting

### Game Doesn't Display in VR

1. Verify you launched Cemu with **`BetterVR LAUNCH CEMU IN VR.bat`** (NOT Cemu.exe directly)
2. The **BetterVR** graphic pack must be enabled in Options → Graphic packs
3. Restart Cemu using the .bat file

### Significant Latency/Lag

1. **Test your connection**:
   - Open the Virtual Desktop overlay
   - Check "Network latency" and "Total latency"
   - If > 50ms, the issue is network-related

2. **Network solutions**:
   - Switch to 5 GHz Wi-Fi
   - Move headset closer to router
   - Verify no one is downloading on your network
   - Restart your router

### Shadow PC Slow / Low FPS

1. Verify Shadow is using the dedicated GPU (not iGPU)
2. Close all background programs
3. Reduce graphical settings in Cemu
4. Contact Shadow support if performance is abnormally low

### Virtual Desktop Doesn't Detect Shadow PC

1. Make sure **Virtual Desktop Streamer** is running on Shadow PC
2. Verify you're using the **same account** on headset and streamer
3. Temporarily disable Windows Firewall on Shadow
4. Restart Virtual Desktop on headset

### Crash at Game Launch

1. Verify **FPS++** is enabled in graphic packs (otherwise guaranteed crash)
2. Make sure Vulkan is selected (not OpenGL)
3. Update community graphic packs
4. Verify your game is version V208 (update 1.5.0)

---

## Commands from Now On

Once everything is configured:

1. **Launch Shadow PC** (from your Shadow app)
2. **Launch Virtual Desktop** on your Quest headset
3. **Connect** to Shadow PC via Virtual Desktop
4. **Double-click** on `BetterVR LAUNCH CEMU IN VR.bat` on the Shadow desktop
5. **Launch the game** from Cemu
6. **Put on the headset** and enjoy! 🎮

---

## Additional Resources

- **Flat2VR Discord**: [https://discord.gg/flat2vr](https://discord.gg/flat2vr) - Community support
- **Cemu Guide**: [https://cemu.cfw.guide/](https://cemu.cfw.guide/)
- **BotW BetterVR GitHub**: [https://github.com/Crementif/BotW-BetterVR](https://github.com/Crementif/BotW-BetterVR)
- **Shadow Support**: [https://help.shadow.tech/](https://help.shadow.tech/)
- **Virtual Desktop Support**: [https://www.vrdesktop.net/](https://www.vrdesktop.net/)

---

## Quick FAQ

**Q: Can I use my PC with Intel i7 13th gen (integrated graphics) instead of Shadow?**  
A: No, Intel integrated graphics are not powerful enough to run Cemu + VR. Shadow PC is necessary.

**Q: Is Virtual Desktop required?**  
A: No, but it's the simplest solution for Quest. You can also use Air Link (Meta) or ALVR (free), but Virtual Desktop generally offers better performance.

**Q: What's the total cost?**  
A: Shadow PC (~$30/month) + Virtual Desktop (~$20 one-time) + BotW game (if you don't have it)

**Q: Can I use a wired PCVR headset instead of Quest?**  
A: Yes! If you have a Valve Index, HP Reverb, etc., connect it directly to Shadow PC (via USB over Network) or to your local PC if it has a sufficient dedicated GPU.

**Q: Is the latency acceptable for playing?**  
A: With a good connection (< 30ms to Shadow, 5GHz Wi-Fi for headset), total latency is 30-50ms, which is acceptable for BotW. Fast-paced games like Beat Saber would be more challenging.

---

**Enjoy VR gaming! 🎮✨**
