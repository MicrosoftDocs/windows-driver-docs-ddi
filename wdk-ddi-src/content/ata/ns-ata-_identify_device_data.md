---
UID: NS:ata._IDENTIFY_DEVICE_DATA
title: _IDENTIFY_DEVICE_DATA
author: windows-driver-content
description: The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\identify_device_data.htm
old-project: storage
ms.assetid: 7f2edd6f-16bf-47a6-8546-7871435a56ac
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _IDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA
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
req.alt-api: IDENTIFY_DEVICE_DATA
req.alt-loc: ata.h
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
req.typenames: IDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA
---

# _IDENTIFY_DEVICE_DATA structure



## -description
The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).



## -syntax

````
typedef struct _IDENTIFY_DEVICE_DATA {
  struct {
    USHORT Reserved1  :1;
    USHORT Retired3  :1;
    USHORT ResponseIncomplete  :1;
    USHORT Retired2  :3;
    USHORT FixedDevice  :1;
    USHORT RemovableMedia  :1;
    USHORT Retired1  :7;
    USHORT DeviceType  :1;
  } GeneralConfiguration;
  USHORT NumCylinders;
  USHORT ReservedWord2;
  USHORT NumHeads;
  USHORT Retired1[2];
  USHORT NumSectorsPerTrack;
  USHORT VendorUnique1[3];
  UCHAR  SerialNumber[20];
  USHORT Retired2[2];
  USHORT Obsolete1;
  UCHAR  FirmwareRevision[8];
  UCHAR  ModelNumber[40];
  UCHAR  MaximumBlockTransfer;
  UCHAR  VendorUnique2;
  USHORT ReservedWord48;
  struct {
    UCHAR  ReservedByte49;
    UCHAR  DmaSupported  :1;
    UCHAR  LbaSupported  :1;
    UCHAR  IordyDisable  :1;
    UCHAR  IordySupported  :1;
    UCHAR  Reserved1  :1;
    UCHAR  StandybyTimerSupport  :1;
    UCHAR  Reserved2  :2;
    USHORT ReservedWord50;
  } Capabilities;
  USHORT ObsoleteWords51[2];
  USHORT TranslationFieldsValid  :3;
  USHORT Reserved3  :13;
  USHORT NumberOfCurrentCylinders;
  USHORT NumberOfCurrentHeads;
  USHORT CurrentSectorsPerTrack;
  ULONG  CurrentSectorCapacity;
  UCHAR  CurrentMultiSectorSetting;
  UCHAR  MultiSectorSettingValid  :1;
  UCHAR  ReservedByte59  :7;
  ULONG  UserAddressableSectors;
  USHORT ObsoleteWord62;
  USHORT MultiWordDMASupport  :8;
  USHORT MultiWordDMAActive  :8;
  USHORT AdvancedPIOModes  :8;
  USHORT ReservedByte64  :8;
  USHORT MinimumMWXferCycleTime;
  USHORT RecommendedMWXferCycleTime;
  USHORT MinimumPIOCycleTime;
  USHORT MinimumPIOCycleTimeIORDY;
  USHORT ReservedWords69[6];
  USHORT QueueDepth  :5;
  USHORT ReservedWord75  :11;
  USHORT ReservedWords76[4];
  USHORT MajorRevision;
  USHORT MinorRevision;
  struct {
    USHORT SmartCommands  :1;
    USHORT SecurityMode  :1;
    USHORT RemovableMediaFeature  :1;
    USHORT PowerManagement  :1;
    USHORT Reserved1  :1;
    USHORT WriteCache  :1;
    USHORT LookAhead  :1;
    USHORT ReleaseInterrupt  :1;
    USHORT ServiceInterrupt  :1;
    USHORT DeviceReset  :1;
    USHORT HostProtectedArea  :1;
    USHORT Obsolete1  :1;
    USHORT WriteBuffer  :1;
    USHORT ReadBuffer  :1;
    USHORT Nop  :1;
    USHORT Obsolete2  :1;
    USHORT DownloadMicrocode  :1;
    USHORT DmaQueued  :1;
    USHORT Cfa  :1;
    USHORT AdvancedPm  :1;
    USHORT Msn  :1;
    USHORT PowerUpInStandby  :1;
    USHORT ManualPowerUp  :1;
    USHORT Reserved2  :1;
    USHORT SetMax  :1;
    USHORT Acoustics  :1;
    USHORT BigLba  :1;
    USHORT DeviceConfigOverlay  :1;
    USHORT FlushCache  :1;
    USHORT FlushCacheExt  :1;
    USHORT Resrved3  :2;
    USHORT SmartErrorLog  :1;
    USHORT SmartSelfTest  :1;
    USHORT MediaSerialNumber  :1;
    USHORT MediaCardPassThrough  :1;
    USHORT StreamingFeature  :1;
    USHORT GpLogging  :1;
    USHORT WriteFua  :1;
    USHORT WriteQueuedFua  :1;
    USHORT WWN64Bit  :1;
    USHORT URGReadStream  :1;
    USHORT URGWriteStream  :1;
    USHORT ReservedForTechReport  :2;
    USHORT IdleWithUnloadFeature  :1;
    USHORT Reserved4  :2;
  } CommandSetSupport;
  struct {
    USHORT SmartCommands  :1;
    USHORT SecurityMode  :1;
    USHORT RemovableMediaFeature  :1;
    USHORT PowerManagement  :1;
    USHORT Reserved1  :1;
    USHORT WriteCache  :1;
    USHORT LookAhead  :1;
    USHORT ReleaseInterrupt  :1;
    USHORT ServiceInterrupt  :1;
    USHORT DeviceReset  :1;
    USHORT HostProtectedArea  :1;
    USHORT Obsolete1  :1;
    USHORT WriteBuffer  :1;
    USHORT ReadBuffer  :1;
    USHORT Nop  :1;
    USHORT Obsolete2  :1;
    USHORT DownloadMicrocode  :1;
    USHORT DmaQueued  :1;
    USHORT Cfa  :1;
    USHORT AdvancedPm  :1;
    USHORT Msn  :1;
    USHORT PowerUpInStandby  :1;
    USHORT ManualPowerUp  :1;
    USHORT Reserved2  :1;
    USHORT SetMax  :1;
    USHORT Acoustics  :1;
    USHORT BigLba  :1;
    USHORT DeviceConfigOverlay  :1;
    USHORT FlushCache  :1;
    USHORT FlushCacheExt  :1;
    USHORT Resrved3  :2;
    USHORT SmartErrorLog  :1;
    USHORT SmartSelfTest  :1;
    USHORT MediaSerialNumber  :1;
    USHORT MediaCardPassThrough  :1;
    USHORT StreamingFeature  :1;
    USHORT GpLogging  :1;
    USHORT WriteFua  :1;
    USHORT WriteQueuedFua  :1;
    USHORT WWN64Bit  :1;
    USHORT URGReadStream  :1;
    USHORT URGWriteStream  :1;
    USHORT ReservedForTechReport  :2;
    USHORT IdleWithUnloadFeature  :1;
    USHORT Reserved4  :2;
  } CommandSetActive;
  USHORT UltraDMASupport  :8;
  USHORT UltraDMAActive  :8;
  USHORT ReservedWord89[4];
  USHORT HardwareResetResult;
  USHORT CurrentAcousticValue  :8;
  USHORT RecommendedAcousticValue  :8;
  USHORT ReservedWord95[5];
  ULONG  Max48BitLBA[2];
  USHORT StreamingTransferTime;
  USHORT ReservedWord105;
  struct {
    USHORT LogicalSectorsPerPhysicalSector  :4;
    USHORT Reserved0  :8;
    USHORT LogicalSectorLongerThan256Words  :1;
    USHORT MultipleLogicalSectorsPerPhysicalSector  :1;
    USHORT Reserved1  :2;
  } PhysicalLogicalSectorSize;
  USHORT InterSeekDelay;
  USHORT WorldWideName[4];
  USHORT ReservedForWorldWideName128[4];
  USHORT ReservedForTlcTechnicalReport;
  USHORT WordsPerLogicalSector[2];
  struct {
    USHORT ReservedForDrqTechnicalReport  :1;
    USHORT WriteReadVerifySupported  :1;
    USHORT Reserved01  :11;
    USHORT Reserved1  :2;
  } CommandSetSupportExt;
  struct {
    USHORT ReservedForDrqTechnicalReport  :1;
    USHORT WriteReadVerifyEnabled  :1;
    USHORT Reserved01  :11;
    USHORT Reserved1  :2;
  } CommandSetActiveExt;
  USHORT ReservedForExpandedSupportandActive[6];
  USHORT MsnSupport  :2;
  USHORT ReservedWord1274  :14;
  struct {
    USHORT SecuritySupported  :1;
    USHORT SecurityEnabled  :1;
    USHORT SecurityLocked  :1;
    USHORT SecurityFrozen  :1;
    USHORT SecurityCountExpired  :1;
    USHORT EnhancedSecurityEraseSupported  :1;
    USHORT Reserved0  :2;
    USHORT SecurityLevel  :1;
    USHORT Reserved1  :7;
  } SecurityStatus;
  USHORT ReservedWord129[31];
  struct {
    USHORT MaximumCurrentInMA2  :12;
    USHORT CfaPowerMode1Disabled  :1;
    USHORT CfaPowerMode1Required  :1;
    USHORT Reserved0  :1;
    USHORT Word160Supported  :1;
  } CfaPowerModel;
  USHORT ReservedForCfaWord161[8];
  struct {
    USHORT SupportsTrim  :1;
    USHORT Reserved0  :15;
  } DataSetManagementFeature;
  USHORT ReservedForCfaWord170[6];
  USHORT CurrentMediaSerialNumber[30];
  USHORT ReservedWord206;
  USHORT ReservedWord207[2];
  struct {
    USHORT AlignmentOfLogicalWithinPhysical  :14;
    USHORT Word209Supported  :1;
    USHORT Reserved0  :1;
  } BlockAlignment;
  USHORT WriteReadVerifySectorCountMode3Only[2];
  USHORT WriteReadVerifySectorCountMode2Only[2];
  struct {
    USHORT NVCachePowerModeEnabled  :1;
    USHORT Reserved0  :3;
    USHORT NVCacheFeatureSetEnabled  :1;
    USHORT Reserved1  :3;
    USHORT NVCachePowerModeVersion  :4;
    USHORT NVCacheFeatureSetVersion  :4;
  } NVCacheCapabilities;
  USHORT NVCacheSizeLSW;
  USHORT NVCacheSizeMSW;
  USHORT NominalMediaRotationRate;
  USHORT ReservedWord218;
  struct {
    UCHAR NVCacheEstimatedTimeToSpinUpInSeconds;
    UCHAR Reserved;
  } NVCacheOptions;
  USHORT ReservedWord220[35];
  USHORT Signature  :8;
  USHORT CheckSum  :8;
} IDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA;
````


## -struct-fields

### -field GeneralConfiguration


### -field Reserved1

Reserved.


### -field Retired3

This member is no longer used.


### -field ResponseIncomplete

Indicates that the response was incomplete.


### -field Retired2

This member is no longer used.


### -field FixedDevice

Indicates when set to 1 that the device is fixed.


### -field RemovableMedia

Indicates when set to 1 that the media is removable.


### -field Retired1

This member is no longer used.


### -field DeviceType

Indicates when set to 1 that the device is an ATA device.

</dd>
</dl>

### -field NumCylinders

Indicates the number of cylinders on the device.


### -field ReservedWord2

Reserved.


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


### -field ReservedWord48

Reserved.


### -field Capabilities


### -field ReservedByte49

Reserved.


### -field DmaSupported

Indicates that the device supports DMA operations.


### -field LbaSupported

Indicates that the device supports logical block addressing.


### -field IordyDisable

Indicates when set to 1 that I/O channel ready is disabled for the device.


### -field IordySupported

Indicates when set to 1 that I/O channel ready is supported by the device.


### -field Reserved1

Reserved.


### -field StandybyTimerSupport

Indicates when set to 1 that the device supports standby timers.


### -field Reserved2

Reserved.


### -field ReservedWord50

Reserved.

</dd>
</dl>

### -field ObsoleteWords51

This member is obsolete. Do not use.


### -field TranslationFieldsValid

Contains a bitfield whose bits indicate which of the bytes in the identify data package contain valid address translation information. For more information about how this bitfield is defined, see the <i>ATA/ATAPI specification</i>.


### -field Reserved3

Reserved.


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


### -field ReservedWords69

Reserved.


### -field QueueDepth

Indicates the maximum queue depth.


### -field ReservedWord75

Reserved.


### -field ReservedWords76

Reserved.


### -field MajorRevision

Indicates the device's major revision number.


### -field MinorRevision

Indicates the device's minor revision number.


### -field CommandSetSupport


### -field SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.


### -field SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.


### -field PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.


### -field Reserved1

Reserved.


### -field WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.


### -field LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.


### -field ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.


### -field ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.


### -field DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.


### -field HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.


### -field Obsolete1

This member is obsolete. Do not use.


### -field WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.


### -field ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.


### -field Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.


### -field Obsolete2

Obsolete. Do not use.


### -field DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.


### -field DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.


### -field Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.


### -field AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.


### -field Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.


### -field PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.


### -field ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.


### -field Reserved2

Reserved.


### -field SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.


### -field Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.


### -field BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.


### -field Resrved3

Reserved.

</dd>
</dl>

### -field CommandSetActive

<dl>


</dl>

### -field SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.


### -field SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.


### -field PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.


### -field Reserved1

Reserved.


### -field WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.


### -field LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.


### -field ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.


### -field ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.


### -field DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.


### -field HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.


### -field Obsolete1

This member is obsolete. Do not use.


### -field WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.


### -field ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.


### -field Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.


### -field Obsolete2

Obsolete. Do not use.


### -field DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.


### -field DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.


### -field Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.


### -field AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.


### -field Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.


### -field PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.


### -field ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.


### -field Reserved2

Reserved.


### -field SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.


### -field Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.


### -field BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.


### -field Resrved3

Reserved.

</dd>
</dl>

### -field UltraDMASupport

Contains a bitmap indicating which ultraDMA modes the device supports.


### -field UltraDMAActive

Contains a bitmap indicating which ultraDMA modes are selected.


### -field ReservedWord89

Reserved.


### -field HardwareResetResult

Indicates the result of a hardware reset. For more information about the values assigned to this member, see the <i>ATA/ATAP specification</i>.


### -field CurrentAcousticValue

Indicates the current acoustic management value.


### -field RecommendedAcousticValue

Contain the device vendor's recommended acoustic management value.


### -field ReservedWord95

Reserved.


### -field Max48BitLBA

Contains the maximum user LBA for the 48-bit address feature set.


### -field StreamingTransferTime


### -field ReservedWord105


### -field PhysicalLogicalSectorSize


### -field Reserved1

Reserved.

</dd>
</dl>

### -field InterSeekDelay


### -field WorldWideName


### -field ReservedForWorldWideName128


### -field ReservedForTlcTechnicalReport


### -field WordsPerLogicalSector


### -field CommandSetSupportExt


### -field Reserved1

Reserved.

</dd>
</dl>

### -field CommandSetActiveExt


### -field Reserved1

Reserved.

</dd>
</dl>

### -field ReservedForExpandedSupportandActive


### -field MsnSupport

Indicates when <b>TRUE</b> that the device supports media status notification.


### -field ReservedWord1274


### -field SecurityStatus

Contains a bitmap that indicates the security status. For more information about the meaning of each individual bit, see the <i>ATA/ATAPI specification</i>.


### -field Reserved1

Reserved.

</dd>
</dl>

### -field ReservedWord129

Reserved.


### -field CfaPowerModel


### -field ReservedForCfaWord161

Words 161-168


### -field DataSetManagementFeature


### -field ReservedForCfaWord170

Words 170-175


### -field CurrentMediaSerialNumber

Words 176-205


### -field ReservedWord206

Word 206


### -field ReservedWord207

Words 207-208


### -field BlockAlignment


### -field WriteReadVerifySectorCountMode3Only

Words 210-211


### -field WriteReadVerifySectorCountMode2Only

Words 212-213


### -field NVCacheCapabilities


### -field Reserved1

Reserved.

</dd>
</dl>

### -field NVCacheSizeLSW


### -field NVCacheSizeMSW


### -field NominalMediaRotationRate


### -field ReservedWord218


### -field NVCacheOptions


### -field ReservedWord220

Words 220-254


### -field Signature

Indicates the disk signature.


### -field CheckSum

Indicates the checksum.


## -remarks
