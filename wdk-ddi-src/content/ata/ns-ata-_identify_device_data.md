---
UID: NS:ata._IDENTIFY_DEVICE_DATA
title: "_IDENTIFY_DEVICE_DATA"
author: windows-driver-content
description: The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\identify_device_data.htm
old-project: storage
ms.assetid: 7f2edd6f-16bf-47a6-8546-7871435a56ac
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PIDENTIFY_DEVICE_DATA, ,, A, C, D, E, F, I, IDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA structure [Storage Devices], N, P, PIDENTIFY_DEVICE_DATA, PIDENTIFY_DEVICE_DATA structure pointer [Storage Devices], T, V, Y, _, _IDENTIFY_DEVICE_DATA, ata/IDENTIFY_DEVICE_DATA, ata/PIDENTIFY_DEVICE_DATA, storage.identify_device_data, structs-ATA_904f6e71-4dd9-4ecb-9928-0d7ce44b83ef.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ata.h
apiname:
-	IDENTIFY_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: IDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA
---

# _IDENTIFY_DEVICE_DATA structure


## -description


The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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


#### - ReservedWord2

Reserved.


#### - ReservedWord48

Reserved.


#### - ReservedWords69

Reserved.


#### - ReservedWords76

Reserved.


#### - ReservedWord89

Reserved.


#### - ReservedWord95

Reserved.


#### - ReservedWord105


#### - ReservedWord1274


#### - CfaPowerModel


#### - ReservedForCfaWord170

Words 170-175


#### - ReservedWord206

Word 206

