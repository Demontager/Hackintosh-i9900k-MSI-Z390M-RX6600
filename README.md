# Hackintosh-i9900k-MSI-Z390M-RX6600
Hackintosh Ventura 13.2.1 on i9900k-MSI-Z390M-RX6600 dGPU


- Motherboard: MSI-Z390-AC-GAMING-EDGE (MS-7B50) Bios ver. 7B50v1C2
- CPU: Intel i9-9900K Coffee Lake  
- RAM: 64GB 4xKHX3000C15/16GX Kingston DDR4
- Storage: Samsung 970 EVO M.2 2TB  
- dGPU: PULSE AMD Radeon™ RX 6600 8Gb
- Broadcom BCM943602CS
- SMIBIOS MacPro7,1
- OpenCore 0.9.0 RELEASE



![Scr18 at 14 32 52](https://user-images.githubusercontent.com/7040503/226106431-2620d418-8a50-4db1-9529-4af5d2b9a527.png)

## Tested and found working:
- Boot into MacOS 13.2.1
- Display Port output
- Internal Audio Realtek ALCS1220A
- Sleep Wake up from bluetooth mouse or keyboard
- dGPU hardware acceleration
- WIFI and Bluetooth  
- Internal Network Card
- Airdrop

This configuration has RX 6600 GPU as main GPU and integrated Intel UHD 630 disabled. 
To get full compatibily with Ventura native WI-FI BCM943602CS used which has been installed in pci-ex slot. No need any additional kext.

![Screenshot 2023-03-18 at 14 32 17](https://user-images.githubusercontent.com/7040503/226106759-9b80bdb5-0877-4bf9-a69c-f2dc9afecfff.png)




## BIOS SETTINGS
###### USB Configuration
- USB Controller [Enabled]
- XHCI Hand-off [Enabled]
- Legacy USB Support [Enabled]

###### PCIe/PCI Sub-system Settings
- Above 4G memory/Crypto Currency mining [Enabled]

Very importan note: Motherboard BIOS has no CFG settings and they are locked by default, this won't allow MacOS to boot at very early stage. To unlock enable these options: edit config.plist and set Kernel -> AppleCpuPmCfgLock YES and AppleXcpCfgLock YES 


Note: USBPorts.kext should be configured on target system to fit desired USB ports map. See: Making own USB port map guides below.



## Tools used:
- [Opencore](https://dortania.github.io/OpenCore-Install-Guide/) 
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/)
- [Hackintool](https://github.com/headkaze/Hackintool)
- [SSDTTime](https://github.com/corpnewt/SSDTTime)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

## Guides:
- [Custom SSDT's with SSDTTime](https://www.tonymacx86.com/threads/custom-ssdts-using-corpnewts-ssdttime.318976/)
- [Making own USB port map](https://www.tonymacx86.com/threads/the-new-beginners-guide-to-usb-port-configuration.286553/#post-2029768)
- [How to map your USB Ports on macOS](https://elitemacx86.com/threads/how-to-map-your-usb-ports-on-macos.581/)

## Motherboard backside:
![usb_map_refrence (1)](https://user-images.githubusercontent.com/7040503/190871487-0bde8041-faaf-4d50-8f83-18f75b65ba53.png)

## Benchmarks
![Screenshot 2023-03-18 at 14 57 56](https://user-images.githubusercontent.com/7040503/226112181-a9183f0e-0d81-4d21-bb5d-ac47009aac9f.png)

![Screenshot 2023-03-18 at 14 59 12](https://user-images.githubusercontent.com/7040503/226112197-311d5c85-76cf-4a80-bfae-cf848025d088.png)
![Screenshot 2023-03-18 at 15 00 03](https://user-images.githubusercontent.com/7040503/226112205-c9d79f7a-43fa-4f22-b8dc-c7cd4c6cfda8.png)


![Screenshot 2023-03-18 at 15 06 39](https://user-images.githubusercontent.com/7040503/226112137-116bccad-b83b-4fa5-aa64-5f28f0229e5b.png)
