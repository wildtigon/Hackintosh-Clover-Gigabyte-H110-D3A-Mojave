# Intel Hackintosh - Clover EFI for Gigabyte H110 series


## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | Intel Celeron G3930 (KabyLake) |
| Motherboard | Gigabyte H110 Series |
| RAM | 16GB (2 x 8GB) |
| Audio Chipset | ALCS-887 |
| GPU | Gigabyte RX 480  |
| Ethernet | RTL8111 1GbE |
| OS Disk (Nvme/Sata3) | Samsung 970 EVO+ 500GB |

**macOS version**: Mojave 10.14.4

## Working
- **Sleep/Wake**
- Ethernet 
	- Settings -> Network -> Ethernet -> Advenced -> Hardware: Set Configure from Automatically->Manually Then set Speed to 1000baseT, click ok and apply.

	- When firts install, you can set via terminal:

		`ifconfig en0 media 1000baseT`

## IMPORTANT
  If you are using Celeron/Pentium for your hackintosh. Please use discrete graphic card and add those lines to this config

  ```
  <key>KernelAndKextPatches</key>
  <dict>
    <key>FakeCPUID</key>
    <string>0x0306A0</string>
  </dict> 
  ```


## How to use
  1. Create directory "EFI" in your EFI partition (e.g. pendrive or hard drive)
  2. Clone this repo and paste directiories "BOOT", "APPLE" and "CLOVER" onto created directory
  3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as model select **iMac17,1**.
  4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values.
  5. Boot it!  

## Disclaimer

This documentation is published for the sole purpose of learning and tech enthusiasm and with no guarantees of any kind, I’m not responsible of any harm of any kind or loss of data that may occur.
