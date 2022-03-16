# Gigabyte Z590 Aorus Pro AX - 11900k - 6800XT
Sharing my Opencore based Hackintosh EFI running great on the i91100k Rocketlake.

# Hardware:

- CPU: Intel i9-11900k stock clock (Overclocking seems to destabilize macOS even if stable on Windows).
- Board: Gigabyte Z590 Aorus Pro AX
- Audio: Realtek ALC4080
- 1x 2.5GBase-T (Intel I225-V)
- 1 x USB Type-C® port on the back panel, with USB 3.2 Gen 2x2 support
- 4 x USB 3.2 Gen 2 Type-A ports (red) on the back panel
- 2 x USB 3.2 Gen 1 ports available through the internal USB header)
- 4 x USB 3.2 Gen1 ports on the back panel
- 8 x USB 2.0/1.1 ports (4 ports on the back panel, 4 ports available through the internal USB headers)
- 4 x M.2 Socket 3 connectors
- RAM: XPG Gammix D30 32GB (16+ 16) DDR4 OC'ed to 3200Mhz CL16 (XMP Profile 1)
- eGPU: ASUS TUF Series AMD Radeon RX 6800 XT 16 GB
- Wifi/BT: Intel AX200. Wifi/BT works fully (including Handoff, Sidecar, etc.) thanks to Airportitlwm.kext. It's native-like.
- SSDs: 1x 500GB Samsung 980 Pro for macOS, 1x 1TB Samsung 980 Pro OEM (PM9A1) for Windows 11
- Case: Deepcool Macube 550P Black Full ATX

# What works:

- SMBIOS: iMacPro1,1 - Full H264/H265 hardware encoding.
- Audio: Works out of the box. Including bluetooth/optical audio.
- USB ports: Ports mapped using USBMap.command, disabled the lowest three USB ports to keep under the 15 port limit.

# What doesn't work:

- Sleep works well, but waking up after an hour or more causes the system to reboot instead of waking up. Working on a fix.
- Waking up from sleep requires power button to be pressed currently. Working on a fix.
- 11th Gen intel internal graphics doesn't (And possibily never will) work due to lack of driver support in macOS. You'll need an external GPU with most Rocketlake CPUs.

# BIOS-settings:

- Current BIOS version: F9a
- Load optimized defaults
- Set Above 4G Decoding to Enabled
- Set Legacy USB Support to Disabled
- Set Intel VT-D to Enabled (DisableIOMapper is disabled, AppleVTD should be working)
- Set Internal Graphics to Disabled (or Auto if you want to use it in Windows)
- For Secure Boot:
- Set Secure Boot to Enabled
- Set Secure Boot Mode to Custom
- Go to Key Management and then Enroll EFI.
Add all *.efi Files in your EFI Folder: BOOTX64.efi, all drivers(OpenRunTime.efi, OpenHFSPlus.efi, OpenCanopy.efi), OpenCore.EFI
FYI: I have XMP Profile disabled because I noticed stability issues in macOS. I am using the RAM with 2133Mhz now.

# Credits:

- **SchmockLord**: This repo is based on his work, shadowing his EFI for the Z590i Vision D. His EFI proved the most stable initially for my slightly different board, from where I made changes.
- **Dortania** for all of their invaluable OpenCore guides.
