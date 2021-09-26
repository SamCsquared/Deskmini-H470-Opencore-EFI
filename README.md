# Deskmini-H470-Opencore-EFI
This is an efi boot sample file for deskmini h470 on opencore 7.3
Hackintosh is highly hardware dependent so you might need to change your config

| Harware  |   My Setup |  comment |
|----------|-------------|------|
| MotherBoard |  Asrock H470-stx | All in one mini PC |
| CPU |    intel i3-10100   |   Comet lake processor |
| CPU cooler| ID-cooling IS-40x | Need to lift the case when installing, fan works without hitting the case|
| GPU | Intergrated UHD630 | Supports up to 3 displays |
| RAM |  Crucial DDR4 3200 8GB SODIMM x2 | Overspect as i3-10100 only supports up to 2666mz on this board |
| Storsage |    Cruicial P5 Nvme 1tb | Picker to login in 13ish seconds |
| Wifi/Bluetooth | BCM94352Z/DW1560 | Sidecar and airdrop works |
| Operating system | Win 10, Big Sur | Dual boot on one nvme drive |

# Hackintosh
1. HDMI and DP boots, type c not rested
2. Sound through HDMI or DP works
3. Sleep/wake works
4. Powermanagement options restored via Dortania's OpenCore Install Guide
5. Update tested(Fine from Big Sur 11.5.2-> 11.6, Opencore 7.2-> 7.3 ok)
6. Airdrop and sidecar works
7. Iservices such as facetime and imessages works as long as you generate your own ROM

# Kexts
To my understanding, kexts are like plugins to pass on hardware information so macOS knows what to do with them. Although SSDTS could serve the same purpose, 
kexts of more modular and more resilent thus less prone to fail when Apple updates. Number of kexts do affect boot time to some degree so you could customize to your own need.

| Kexts |      comment |
|----------|-------------|
| AirportBrcmFixup | Fix wifi for Broadcom wifi/BT cards | 
| AppleALC | Apple sound codecs |   
| BrcmBluetoothInjector| Fix Bluetooth for Broadcom wifi/BT cards | 
| BrcmFirmwareData | Fix Bluetooth for Broadcom wifi/BT cards |
| BrcmPatchRAM3 |  Fix Bluetooth for Broadcom wifi/BT cards | 
| CPUFriendDataProvider | Power/Energy saving management options |
| FeatureUnlock | Allows AirPlay to Mac, Sidecar and Universal Control Unlock, NightShift Unlock on older models | 
| IntelMausi| Intel Ethernet LAN driver for macOS |
| Lilu | Arbitrary kext and process patching on macOS |
| NVMeFix |  Patches for the Apple NVMe storage driver | 
| SMCSuperIO |  Monitor hardware informations |
| USBPorts | Allows proper USB mappings for speed and bluetooth | 
| VirtualSMC | Apple SMC emulator |
| WhateverGreen | GPU, display related | 


# Known issues
1. When booting with dual screen on, horizontal stripes/artifacts appears on screen which can be solved by repluging the moniter or turn on screen after login
2. Popping/ hissing sound for speakers/headphone when booting, shutting down or sleeping, no issues when using macOS
3. DRM contents such as Netflix is not playable on Safari, use Firefox, Chrome or Edge instead.(As of Big Sur, DRM are baked in Apple's hardware)

# To be done in the future
1. Bulid my own custom SSDTs
2. Follow up on display fixes and sound fixes

# Debugging 
1. Always try resetting NVRAM first
2. Change opencore to debug version and try to follow Dortania's guide
