# OpenCore-Catalina-10.15.4

[Hardware](README.md#Hardware)

[Misc](README.md#Misc)

[Drivers](README.md#Drivers)

[Kexts](README.md#Kexts)

[SSDT](README.md#SSDT)

[Config](README.md#Config)

[BIOS Settings 4.40](README.md#BIOS-Settings)

## Hardware

**CPU:** Intel Core i5-9400F 2.9 GHz 6-Core Processor

**Video Card:** Sapphire Radeon RX 5500 XT 8 GB PULSE

**Memory:** Corsair Vengeance LPX 16 GB (2 x 8 GB) DDR4-2666

**Motherboard:** ASRock Z390 Phantom Gaming-ITX/ac Mini ITX 

**Audio Codec:** ALC1220

**Ethernet Card:** Intel I219V7

**Wifi/BT Card:** N/A

**Guide:** [OpenCore 0.5.7](https://dortania.github.io/OpenCore-Desktop-Guide/)

## Misc

**Storage:** Patriot Scorch 256 GB M.2-2280 NVME

**Storage:** Silicon Power A60 256 GB M.2-2280 NVME

**Case:** Fractal Design Node 202

**Power Supply:** Corsair SF 600 W 80+ Platinum

**Monitor:** Asus VS228H-P 21.5" 1920x1080 Monitor

## Drivers

- [ApfsDriverLoader.efi](https://github.com/acidanthera/AppleSupportPkg/releases)
- [HfsPlus.efi](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
- [OpenRuntime.efi](https://github.com/acidanthera/OpenCorePkg/releases)

## Kexts

- [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)
- [Lilu](https://github.com/vit9696/Lilu/releases)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases)
- [AppleALC](https://github.com/vit9696/AppleALC/releases)
- [IntelMausiEthernet](https://github.com/Mieze/IntelMausiEthernet)
- [SmallTreeIntel82576](https://github.com/khronokernel/SmallTree-I211-AT-patch/releases)
- [XHCI-unsupported](https://github.com/RehabMan/OS-X-USB-Inject-All)

## SSDT

- [SSDT-PLUG](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/SSDT-PLUG.dsl)
- [SSDT-EC-USBX](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/SSDT-EC-USBX.dsl)
- [SSDT-AWAC](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/SSDT-AWAC.dsl)
- [SSDT-PMC](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/SSDT-PMC.dsl)
- [SSDT-TB3](SSDT-Z390-ASRock-ITX-AR-TB3-V8.aml)

## Config

[config.plist](SanityCheck.md)

### Main Changes

1. ###### DeviceProperties -> Add -> PciRoot(0x0)/Pci(0x2,0x0) -> AAPL,ig-platform-id

   - `0300913E`

2. ###### Kernel -> Quirks -> AppleCpuPmCfgLock, AppleXcpmCfgLock

   - `FALSE`

3. ###### Kernel -> Quirks -> DisableIoMapper, XhciPortLimit

   - `TRUE`

4. ###### Misc -> Security -> AllowNvramReset, AllowSetDefault

   - `TRUE`

5. ###### Misc -> Security -> AuthRestart

   - `FALSE`

6. ###### Misc -> Security -> ExposeSensitiveData

   - `6`

7. ###### Misc -> Security -> Vault

   - `Optional`

8. ###### Misc -> Security -> ScanPolicy

   - `0`

9. ###### NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> boot-args

   - `-v keepsyms=1 debug=0x100 alcid=1 agdpmod=pikera`

## BIOS Settings

- #### CPU Configuration

  - CFG Lock `Disabled`
  - Intel SGX `Enabled`

- #### Chipset Configuration

  - Above 4G Decoding `Enabled`
  - Vt-d `Enabled`

- ### Intel Thunderbolt

  - Thunderbolt Support `Enabled`
  - Thunderbolt Boot Support `Boot once`
  - Thunderbolt Usb Support `Enabled`

- ### USB Configuration

  - XHCI Hand-off `Enabled`

- ### Security

  - Intel Platform Trust Technology `Disabled`

- ### Boot

  - Fast Boot `Disabled`

- ### CSM

  - CSM `Disabled`
