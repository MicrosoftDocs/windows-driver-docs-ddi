---
UID: NS:ata._IDENTIFY_DEVICE_DATA
title: "_IDENTIFY_DEVICE_DATA"
author: windows-driver-content
description: The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\identify_device_data.htm
old-project: storage
ms.assetid: 7f2edd6f-16bf-47a6-8546-7871435a56ac
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PIDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA structure [Storage Devices], PIDENTIFY_DEVICE_DATA, PIDENTIFY_DEVICE_DATA structure pointer [Storage Devices], _IDENTIFY_DEVICE_DATA, ata/IDENTIFY_DEVICE_DATA, ata/PIDENTIFY_DEVICE_DATA, storage.identify_device_data, structs-ATA_904f6e71-4dd9-4ecb-9928-0d7ce44b83ef.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ata.h
req.include-header: Irb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ata.h
api_name:
-	IDENTIFY_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: IDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA
---

# _IDENTIFY_DEVICE_DATA structure


## -description


The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field GeneralConfiguration



#### Reserved1

Reserved.



#### Retired3

This member is no longer used.



#### ResponseIncomplete

Indicates that the response was incomplete.



#### Retired2

This member is no longer used.



#### FixedDevice

Indicates when set to 1 that the device is fixed.



#### RemovableMedia

Indicates when set to 1 that the media is removable.



#### Retired1

This member is no longer used.



#### DeviceType

Indicates when set to 1 that the device is an ATA device.


### -field NumCylinders

Indicates the number of cylinders on the device.


### -field SpecificConfiguration

 


### -field NumHeads

Number of logical heads on the device.


### -field Retired1

This member is no longer used.


### -field NumSectorsPerTrack

Indicates the number of sectors per track.


### -field VendorUnique1

Contains the first ID of the device's vendor.


### -field SerialNumber

Contains the serial number of the device.


### -field Retired2

This member is no longer used.


### -field Obsolete1

This member is obsolete. Do not use.


### -field FirmwareRevision

Contains the revision number of the device's firmware.


### -field ModelNumber

Contains the device's model number.


### -field MaximumBlockTransfer

Contains the maximum number of blocks allowed in a single transfer.


### -field VendorUnique2

Contains the second ID of the device's vendor.


### -field TrustedComputing

 


### -field Capabilities



#### ReservedByte49

Reserved.



#### DmaSupported

Indicates that the device supports DMA operations.



#### LbaSupported

Indicates that the device supports logical block addressing.



#### IordyDisable

Indicates when set to 1 that I/O channel ready is disabled for the device.



#### IordySupported

Indicates when set to 1 that I/O channel ready is supported by the device.



#### Reserved1

Reserved.



#### StandybyTimerSupport

Indicates when set to 1 that the device supports standby timers.



#### Reserved2

Reserved.



#### ReservedWord50

Reserved.


### -field ObsoleteWords51

This member is obsolete. Do not use.


### -field TranslationFieldsValid

Contains a bitfield whose bits indicate which of the bytes in the identify data package contain valid address translation information. For more information about how this bitfield is defined, see the <i>ATA/ATAPI specification</i>.


### -field Reserved3

Reserved.


### -field FreeFallControlSensitivity

 


### -field NumberOfCurrentCylinders

Indicates the number of cylinders on the device.


### -field NumberOfCurrentHeads

Indicates the number of heads on the device.


### -field CurrentSectorsPerTrack

Indicates the number of sectors per track.


### -field CurrentSectorCapacity

Indicates the number of sectors on the device.


### -field CurrentMultiSectorSetting

Indicates the multisector setting.


### -field MultiSectorSettingValid

Indicates when <b>TRUE</b> that the multisector setting is valid.


### -field ReservedByte59

Reserved.


### -field SanitizeFeatureSupported

 


### -field CryptoScrambleExtCommandSupported

 


### -field OverwriteExtCommandSupported

 


### -field BlockEraseExtCommandSupported

 


### -field UserAddressableSectors

Indicates the total number of user-addressable sectors.


### -field ObsoleteWord62

This member is obsolete. Do not use.


### -field MultiWordDMASupport

Indicates which DMA modes the device supports.


### -field MultiWordDMAActive

Indicates which DMA modes are currently selected.


### -field AdvancedPIOModes


### -field ReservedByte64

Reserved.


### -field MinimumMWXferCycleTime

Indicates the minimum multiword DMA transfer cycle time per word.


### -field RecommendedMWXferCycleTime

Indicates the recommended multiword DMA transfer cycle time per word.


### -field MinimumPIOCycleTime

Indicates the minimum PIO transfer cycle time without flow control.


### -field MinimumPIOCycleTimeIORDY

Indicates the minimum PIO transfer cycle time with IORDY flow control.


### -field AdditionalSupported

 


### -field ReservedWords70

 


### -field QueueDepth

Indicates the maximum queue depth.


### -field ReservedWord75

Reserved.


### -field SerialAtaCapabilities

 


### -field SerialAtaFeaturesSupported

 


### -field SerialAtaFeaturesEnabled

 


### -field MajorRevision

Indicates the device's major revision number.


### -field MinorRevision

Indicates the device's minor revision number.


### -field CommandSetSupport



#### SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.



#### SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.



#### PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.



#### Reserved1

Reserved.



#### WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.



#### LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.



#### ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.



#### ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.



#### DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.



#### HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.



#### Obsolete1

This member is obsolete. Do not use.



#### WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.



#### ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.



#### Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.



#### Obsolete2

Obsolete. Do not use.



#### DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.



#### DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.



#### Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.



#### AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.



#### Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.



#### PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.



#### ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.



#### Reserved2

Reserved.



#### SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.



#### Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.



#### BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.



#### Resrved3

Reserved.


### -field CommandSetActive



#### 



#### SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.



#### SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.



#### PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.



#### Reserved1

Reserved.



#### WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.



#### LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.



#### ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.



#### ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.



#### DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.



#### HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.



#### Obsolete1

This member is obsolete. Do not use.



#### WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.



#### ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.



#### Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.



#### Obsolete2

Obsolete. Do not use.



#### DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.



#### DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.



#### Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.



#### AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.



#### Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.



#### PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.



#### ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.



#### Reserved2

Reserved.



#### SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.



#### Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.



#### BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.



#### Resrved3

Reserved.


### -field UltraDMASupport

Contains a bitmap indicating which ultraDMA modes the device supports.


### -field UltraDMAActive

Contains a bitmap indicating which ultraDMA modes are selected.


### -field NormalSecurityEraseUnit

 


### -field EnhancedSecurityEraseUnit

 


### -field CurrentAPMLevel

 


### -field ReservedWord91

 


### -field MasterPasswordID

 


### -field HardwareResetResult

Indicates the result of a hardware reset. For more information about the values assigned to this member, see the <i>ATA/ATAP specification</i>.


### -field CurrentAcousticValue

Indicates the current acoustic management value.


### -field RecommendedAcousticValue

Contain the device vendor's recommended acoustic management value.


### -field StreamMinRequestSize

 


### -field StreamingTransferTimeDMA

 


### -field StreamingAccessLatencyDMAPIO

 


### -field StreamingPerfGranularity

 


### -field Max48BitLBA

Contains the maximum user LBA for the 48-bit address feature set.


### -field StreamingTransferTime


### -field DsmCap

 


### -field PhysicalLogicalSectorSize



#### Reserved1

Reserved.


### -field InterSeekDelay


### -field WorldWideName


### -field ReservedForWorldWideName128


### -field ReservedForTlcTechnicalReport


### -field WordsPerLogicalSector


### -field CommandSetSupportExt



#### Reserved1

Reserved.


### -field CommandSetActiveExt



#### Reserved1

Reserved.


### -field ReservedForExpandedSupportandActive


### -field MsnSupport

Indicates when <b>TRUE</b> that the device supports media status notification.


### -field ReservedWord127

 


### -field SecurityStatus

Contains a bitmap that indicates the security status. For more information about the meaning of each individual bit, see the <i>ATA/ATAPI specification</i>.



#### Reserved1

Reserved.


### -field ReservedWord129

Reserved.


### -field CfaPowerMode1

 


### -field ReservedForCfaWord161

Words 161-168


### -field NominalFormFactor

 


### -field ReservedWord168

 


### -field DataSetManagementFeature


### -field AdditionalProductID

 


### -field ReservedForCfaWord174

 


### -field CurrentMediaSerialNumber

Words 176-205


### -field SCTCommandTransport

 


### -field ReservedWord207

Words 207-208


### -field BlockAlignment


### -field WriteReadVerifySectorCountMode3Only

Words 210-211


### -field WriteReadVerifySectorCountMode2Only

Words 212-213


### -field NVCacheCapabilities



#### Reserved1

Reserved.


### -field NVCacheSizeLSW


### -field NVCacheSizeMSW


### -field NominalMediaRotationRate


### -field ReservedWord218


### -field NVCacheOptions


### -field WriteReadVerifySectorCountMode

 


### -field ReservedWord220

Words 220-254


### -field ReservedWord221

 


### -field TransportMajorVersion

 


### -field TransportMinorVersion

 


### -field ReservedWord224

 


### -field ExtendedNumberOfUserAddressableSectors

 


### -field MinBlocksPerDownloadMicrocodeMode03

 


### -field MaxBlocksPerDownloadMicrocodeMode03

 


### -field ReservedWord236

 


### -field Signature

Indicates the disk signature.


### -field CheckSum

Indicates the checksum.


#### - CfaPowerModel


#### - ReservedForCfaWord170

Words 170-175


#### - ReservedWord105


#### - ReservedWord1274


#### - ReservedWord2

Reserved.


#### - ReservedWord206

Word 206


#### - ReservedWord48

Reserved.


#### - ReservedWord89

Reserved.


#### - ReservedWord95

Reserved.


#### - ReservedWords69

Reserved.


#### - ReservedWords76

Reserved.

