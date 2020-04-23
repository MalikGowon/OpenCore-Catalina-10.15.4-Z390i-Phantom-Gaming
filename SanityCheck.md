## ACPI

### Add

- **SSDT-AWAC.aml** Make sure this file is in your OC/ACPI directory
- **SSDT-EC-USBX.aml** Make sure this file is in your OC/ACPI directory
- **SSDT-PLUG.aml** Make sure this file is in your OC/ACPI directory
- **SSDT-PMC.aml** Make sure this file is in your OC/ACPI directory
- **SSDT-Z390-ASRock-ITX-AR-TB3-V8.aml** Make sure this file is in your OC/ACPI directory

### Block

### Patch

### Quirks

- **FadtEnableReset** = **No**
- **NormalizeHeaders** = **No**
- **RebaseRegions** = **No**
- **ResetHwSig** = **No**
- **ResetLogoStatus** = **No**

## Booter

### MmioWhitelist

### Quirks

- **AvoidRuntimeDefrag** = **Yes**
- **DevirtualiseMmio** = **Yes**
- **DisableSingleUser** = **No**
- **DisableVariableWrite** = **No**
- **DiscardHibernateMap** = **No**
- **EnableSafeModeSlide** = **Yes**
- **EnableWriteUnprotector** = **Yes**
- **ForceExitBootServices** = **No**
- **ProtectMemoryRegions** = **No**
- **ProtectSecureBoot** = **No**
- **ProtectUefiServices** = **No**
- **ProvideCustomSlide** = **Yes**
- **RebuildAppleMemoryMap** = **Yes**
- **SetupVirtualMap** = **No** but should normally be **Yes**
- **ShrinkMemoryMap** is missing. Normally set to **No**
- **SignalAppleOS** = **No**
- **SyncRuntimePermissions** = **Yes**

## DeviceProperties

### Add

- **AAPL,ig-platform-id** = **0300913e** iGPU set correctly

### Block

## Kernel

### Add

- **Lilu.kext** make sure this Kext is in your **OC/Kexts** directory and the first kext listed here
- **XHCI-unsupported.kext** you probably don't need this
- **VirtualSMC.kext** make sure this Kext is in your **OC/Kexts** directory
- **AppleALC.kext** make sure this Kext is in your **OC/Kexts** directory
- **SmallTreeIntel82576.kext** make sure this Kext is in your **OC/Kexts** directory
- **WhateverGreen.kext** make sure this Kext is in your **OC/Kexts** directory
- **IntelMausi.kext** make sure this Kext is in your **OC/Kexts** directory

### Block

### Emulate

### Patch

### Quirks

- **AppleCpuPmCfgLock** = **No** Make sure CFG-Lock is disabled in your bios
- **AppleXcpmCfgLock** = **No** Make sure CFG-Lock is disabled in your bios
- **AppleXcpmExtraMsrs** = **No**
- **AppleXcpmForceBoost** = **No**
- **CustomSMBIOSGuid** = **No**
- **DisableIoMapper** = **Yes**
- **DummyPowerManagement** = **No**
- **ExternalDiskIcons** = **No**
- **IncreasePciBarSize** = **No**
- **LapicKernelPanic** = **No**
- **PanicNoKextDump** = **Yes**
- **PowerTimeoutKernelPanic** = **Yes**
- **ThirdPartyDrives** = **No**
- **XhciPortLimit** = **Yes** turn off after USB port mapping

## Misc

### BlessOverride

### Boot

- **HideSelf** = **Yes**
- **ConsoleAttributes** = **0**
- **PollAppleHotKeys** = **No**
- **ShowPicker** = **Yes**
- **TakeoffDelay** = **0**
- **HibernateMode** = **None**
- **PickerMode** = **Builtin**
- **HideAuxiliary** = **No**
- **PickerAttributes** = **0**
- **PickerAudioAssist** = **No**
- **Timeout** = **5**

### Debug

- **AppleDebug** = **Yes**
- **DisableWatchDog** = **Yes**
- **Target** = **67**
- **DisplayLevel** see [Debugging Docs](https://desktop.dortania.ml/troubleshooting/debug.html) for more info debug display levels
- **DisplayDelay** = **0**

### Entries

### Security

- **AllowNvramReset** = **Yes**
- **AllowSetDefault** = **Yes**
- **AuthRestart** = **No**
- **Vault** = **Optional**
- **HaltLevel** = **2147483648**
- **ExposeSensitiveData** = **6**
- **ScanPolicy** = **0**

### Tools

- You can remove the tool EFIs here

## NVRAM

- **LegacyEnable** = **No**
- **LegacyOverwrite** = **No**
- **WriteFlash** = **Yes**

### Add

- **UIScale** = **01**
- **DefaultBackgroundColor** = **00000000**
- **boot-args** = **-v keepsyms=1 debug=0x100 alcid=1 agdpmod=pikera**
- **csr-active-config** = **00000000**
- **prev-lang:kbd** = **656e2d55533a30 (en-US:0)**
- **SystemAudioVolume** = **46**

### Block

### LegacySchema

## PlatformInfo

- **Automatic** = **Yes**
- **UpdateDataHub** = **Yes**
- **UpdateNVRAM** = **Yes**
- **UpdateSMBIOS** = **Yes**
- **UpdateSMBIOSMode** = **Create**

### DataHub

### Generic

- **SpoofVendor** = **Yes**
- **AdviseWindows** = **No**
- **SystemProductName** = **iMac19,1**
- **MLB** is set
- **ROM** is set
- **SystemSerialNumber** is set
- **SystemUUID** is set

### PlatformNVRAM

### SMBIOS

## UEFI

- **ConnectDrivers** = **Yes**

### Drivers

- **HfsPlus.efi**
- **OpenRuntime.efi**
- **ApfsDriverLoader.efi**

### Audio

- **AudioSupport** = **No**
- **AudioDevice** = **PciRoot(0x0)/Pci(0x1b,0x0)**
- **AudioCodec** = **0**
- **AudioOut** = **0**
- **MinimumVolume** = **20**
- **PlayChime** = **No**
- **VolumeAmplifier** = **0**

### Input

- **KeyFiltering** = **No**
- **KeyForgetThreshold** = **5**
- **KeyMergeThreshold** = **2**
- **KeySupport** = **Yes**
- **KeySupportMode** = **Auto**
- **KeySwap** = **Yes** but should normally be **No**
- **PointerSupport** = **No**
- **PointerSupportMode** = ***-blank-\***
- **TimerResolution** = **50000**

### Output

- **TextRenderer** = **BuiltinGraphics**
- **ConsoleMode** = ***-blank-\***
- **Resolution** = **Max**
- **ClearScreenOnModeSwitch** = **No**
- **IgnoreTextInGraphics** = **No**
- **ProvideConsoleGop** = **Yes**
- **DirectGopRendering** = **No**
- **DirectGopCacheMode** = ***-blank-\***
- **ReconnectOnResChange** = **No**
- **ReplaceTabWithSpace** = **No**
- **SanitiseClearScreen** = **No**

### Protocols

- **AppleAudio** = **No**
- **AppleBootPolicy** = **No**
- **AppleDebugLog** = **No**
- **AppleEvent** = **No**
- **AppleImageConversion** = **No**
- **AppleKeyMap** = **No**
- **AppleSmcIo** = **No**
- **DataHub** = **No**
- **DeviceProperties** = **No**
- **FirmwareVolume** = **No**
- **HashServices** = **No**
- **OSInfo** = **No**
- **UnicodeCollation** = **No**

### Quirks

- **ExitBootServicesDelay** = **0**
- **IgnoreInvalidFlexRatio** = **No**
- **ReleaseUsbOwnership** = **No**
- **RequestBootVarFallback** = **Yes**
- **RequestBootVarRouting** = **Yes**
- **UnblockFsConnect** = **No**
