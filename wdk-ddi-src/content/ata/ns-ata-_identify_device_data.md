---
UID: NS:ata._IDENTIFY_DEVICE_DATA
title: "_IDENTIFY_DEVICE_DATA"
author: windows-driver-content
description: The IDENTIFY_DEVICE_DATA structure contains the data retrieved by an ATA identify device data command (0xEC).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\identify_device_data.htm
old-project: storage
ms.assetid: 7f2edd6f-16bf-47a6-8546-7871435a56ac
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_IDENTIFY_DEVICE_DATA, structs-ATA_904f6e71-4dd9-4ecb-9928-0d7ce44b83ef.xml, ata/IDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA, PIDENTIFY_DEVICE_DATA structure pointer [Storage Devices], storage.identify_device_data, PIDENTIFY_DEVICE_DATA, *PIDENTIFY_DEVICE_DATA, IDENTIFY_DEVICE_DATA structure [Storage Devices], ata/PIDENTIFY_DEVICE_DATA"
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



### -field GeneralConfiguration.Reserved1

Reserved.


### -field GeneralConfiguration.Retired3

This member is no longer used.


### -field GeneralConfiguration.ResponseIncomplete

Indicates that the response was incomplete.


### -field GeneralConfiguration.Retired2

This member is no longer used.


### -field GeneralConfiguration.FixedDevice

Indicates when set to 1 that the device is fixed.


### -field GeneralConfiguration.RemovableMedia

Indicates when set to 1 that the media is removable.


### -field GeneralConfiguration.Retired1

This member is no longer used.


### -field GeneralConfiguration.DeviceType

Indicates when set to 1 that the device is an ATA device.


### -field TrustedComputing

 


### -field TrustedComputing.FeatureSupported

 


### -field TrustedComputing.Reserved

 


### -field Capabilities



### -field Capabilities.CurrentLongPhysicalSectorAlignment

 


### -field Capabilities.ReservedByte49

Reserved.


### -field Capabilities.DmaSupported

Indicates that the device supports DMA operations.


### -field Capabilities.LbaSupported

Indicates that the device supports logical block addressing.


### -field Capabilities.IordyDisable

Indicates when set to 1 that I/O channel ready is disabled for the device.


### -field Capabilities.IordySupported

Indicates when set to 1 that I/O channel ready is supported by the device.


### -field Capabilities.Reserved1

Reserved.


### -field Capabilities.StandybyTimerSupport

Indicates when set to 1 that the device supports standby timers.


### -field Capabilities.Reserved2

Reserved.


### -field Capabilities.ReservedWord50

Reserved.


### -field AdditionalSupported

 


### -field AdditionalSupported.ZonedCapabilities

 


### -field AdditionalSupported.NonVolatileWriteCache

 


### -field AdditionalSupported.ExtendedUserAddressableSectorsSupported

 


### -field AdditionalSupported.DeviceEncryptsAllUserData

 


### -field AdditionalSupported.ReadZeroAfterTrimSupported

 


### -field AdditionalSupported.Optional28BitCommandsSupported

 


### -field AdditionalSupported.IEEE1667

 


### -field AdditionalSupported.DownloadMicrocodeDmaSupported

 


### -field AdditionalSupported.SetMaxSetPasswordUnlockDmaSupported

 


### -field AdditionalSupported.WriteBufferDmaSupported

 


### -field AdditionalSupported.ReadBufferDmaSupported

 


### -field AdditionalSupported.DeviceConfigIdentifySetDmaSupported

 


### -field AdditionalSupported.LPSAERCSupported

 


### -field AdditionalSupported.DeterministicReadAfterTrimSupported

 


### -field AdditionalSupported.CFastSpecSupported

 


### -field SerialAtaCapabilities

 


### -field SerialAtaCapabilities.Reserved0

 


### -field SerialAtaCapabilities.SataGen1

 


### -field SerialAtaCapabilities.SataGen2

 


### -field SerialAtaCapabilities.SataGen3

 


### -field SerialAtaCapabilities.Reserved1

 


### -field SerialAtaCapabilities.NCQ

 


### -field SerialAtaCapabilities.HIPM

 


### -field SerialAtaCapabilities.PhyEvents

 


### -field SerialAtaCapabilities.NcqUnload

 


### -field SerialAtaCapabilities.NcqPriority

 


### -field SerialAtaCapabilities.HostAutoPS

 


### -field SerialAtaCapabilities.DeviceAutoPS

 


### -field SerialAtaCapabilities.ReadLogDMA

 


### -field SerialAtaCapabilities.Reserved2

 


### -field SerialAtaCapabilities.CurrentSpeed

 


### -field SerialAtaCapabilities.NcqStreaming

 


### -field SerialAtaCapabilities.NcqQueueMgmt

 


### -field SerialAtaCapabilities.NcqReceiveSend

 


### -field SerialAtaCapabilities.DEVSLPtoReducedPwrState

 


### -field SerialAtaCapabilities.Reserved3

 


### -field SerialAtaFeaturesSupported

 


### -field SerialAtaFeaturesSupported.Reserved0

 


### -field SerialAtaFeaturesSupported.NonZeroOffsets

 


### -field SerialAtaFeaturesSupported.DmaSetupAutoActivate

 


### -field SerialAtaFeaturesSupported.DIPM

 


### -field SerialAtaFeaturesSupported.InOrderData

 


### -field SerialAtaFeaturesSupported.HardwareFeatureControl

 


### -field SerialAtaFeaturesSupported.SoftwareSettingsPreservation

 


### -field SerialAtaFeaturesSupported.NCQAutosense

 


### -field SerialAtaFeaturesSupported.DEVSLP

 


### -field SerialAtaFeaturesSupported.HybridInformation

 


### -field SerialAtaFeaturesSupported.Reserved1

 


### -field SerialAtaFeaturesEnabled

 


### -field SerialAtaFeaturesEnabled.Reserved0

 


### -field SerialAtaFeaturesEnabled.NonZeroOffsets

 


### -field SerialAtaFeaturesEnabled.DmaSetupAutoActivate

 


### -field SerialAtaFeaturesEnabled.DIPM

 


### -field SerialAtaFeaturesEnabled.InOrderData

 


### -field SerialAtaFeaturesEnabled.HardwareFeatureControl

 


### -field SerialAtaFeaturesEnabled.SoftwareSettingsPreservation

 


### -field SerialAtaFeaturesEnabled.DeviceAutoPS

 


### -field SerialAtaFeaturesEnabled.DEVSLP

 


### -field SerialAtaFeaturesEnabled.HybridInformation

 


### -field SerialAtaFeaturesEnabled.Reserved1

 


### -field CommandSetSupport



#### Resrved3

Reserved.


### -field CommandSetSupport.SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.


### -field CommandSetSupport.SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.


### -field CommandSetSupport.RemovableMediaFeature

 


### -field CommandSetSupport.PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.


### -field CommandSetSupport.Reserved1

Reserved.


### -field CommandSetSupport.WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.


### -field CommandSetSupport.LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.


### -field CommandSetSupport.ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.


### -field CommandSetSupport.ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.


### -field CommandSetSupport.DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.


### -field CommandSetSupport.HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.


### -field CommandSetSupport.Obsolete1

This member is obsolete. Do not use.


### -field CommandSetSupport.WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.


### -field CommandSetSupport.ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.


### -field CommandSetSupport.Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.


### -field CommandSetSupport.Obsolete2

Obsolete. Do not use.


### -field CommandSetSupport.DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.


### -field CommandSetSupport.DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.


### -field CommandSetSupport.Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.


### -field CommandSetSupport.AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.


### -field CommandSetSupport.Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.


### -field CommandSetSupport.PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.


### -field CommandSetSupport.ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.


### -field CommandSetSupport.Reserved2

Reserved.


### -field CommandSetSupport.SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.


### -field CommandSetSupport.Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.


### -field CommandSetSupport.BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.


### -field CommandSetSupport.DeviceConfigOverlay

 


### -field CommandSetSupport.FlushCache

 


### -field CommandSetSupport.FlushCacheExt

 


### -field CommandSetSupport.WordValid83

 


### -field CommandSetSupport.SmartErrorLog

 


### -field CommandSetSupport.SmartSelfTest

 


### -field CommandSetSupport.MediaSerialNumber

 


### -field CommandSetSupport.MediaCardPassThrough

 


### -field CommandSetSupport.StreamingFeature

 


### -field CommandSetSupport.GpLogging

 


### -field CommandSetSupport.WriteFua

 


### -field CommandSetSupport.WriteQueuedFua

 


### -field CommandSetSupport.WWN64Bit

 


### -field CommandSetSupport.URGReadStream

 


### -field CommandSetSupport.URGWriteStream

 


### -field CommandSetSupport.ReservedForTechReport

 


### -field CommandSetSupport.IdleWithUnloadFeature

 


### -field CommandSetSupport.WordValid

 


### -field CommandSetActive



#### 



### -field CommandSetActive.SmartCommands

Indicates when <b>TRUE</b> that the device supports the SMART feature set.


### -field CommandSetActive.SecurityMode

Indicates when <b>TRUE</b> that the device supports the security mode feature set.


### -field CommandSetActive.RemovableMediaFeature

 


### -field CommandSetActive.PowerManagement

Indicates when <b>TRUE</b> that the device supports the mandatory power management feature set.


### -field CommandSetActive.Reserved1

Reserved.


### -field CommandSetActive.WriteCache

Indicates when <b>TRUE</b> that the device supports a write cache.


### -field CommandSetActive.LookAhead

Indicates when <b>TRUE</b> that the device supports lookahead.


### -field CommandSetActive.ReleaseInterrupt

Indicates when <b>TRUE</b> that the device supports release interrupt.


### -field CommandSetActive.ServiceInterrupt

Indicates when <b>TRUE</b> that the device supports service interrupt.


### -field CommandSetActive.DeviceReset

Indicates when <b>TRUE</b> that the device supports the device reset command.


### -field CommandSetActive.HostProtectedArea

Indicates when <b>TRUE</b> that the device supports the host protected area feature set.


### -field CommandSetActive.Obsolete1

This member is obsolete. Do not use.


### -field CommandSetActive.WriteBuffer

Indicates when <b>TRUE</b> that the device supports the write buffer command.


### -field CommandSetActive.ReadBuffer

Indicates when <b>TRUE</b> that the device supports the read buffer command.


### -field CommandSetActive.Nop

Indicates when <b>TRUE</b> that the device supports the NOP command.


### -field CommandSetActive.Obsolete2

Obsolete. Do not use.


### -field CommandSetActive.DownloadMicrocode

Indicates when <b>TRUE</b> that the device supports the DOWNLOAD MICROCODE command.


### -field CommandSetActive.DmaQueued

Indicates when <b>TRUE</b> that the device supports READ/WRITE DMA QUEUED command.


### -field CommandSetActive.Cfa

Indicates when <b>TRUE</b> that the device supports the CFA feature set.


### -field CommandSetActive.AdvancedPm

Indicates when <b>TRUE</b> that the device supports the advanced power management feature set.


### -field CommandSetActive.Msn

Indicates when <b>TRUE</b> that the device supports the media status notification feature set.


### -field CommandSetActive.PowerUpInStandby

Indicates when <b>TRUE</b> that the device supports power-up in standby feature set.


### -field CommandSetActive.ManualPowerUp

Indicates when <b>TRUE</b> that the device supports the SET FEATURES subcommand required to spin up the device after power-up.


### -field CommandSetActive.Reserved2

Reserved.


### -field CommandSetActive.SetMax

Indicates when <b>TRUE</b> that the device supports the SET MAX security extension command.


### -field CommandSetActive.Acoustics

Indicates when <b>TRUE</b> that the device supports the automatic acoustic management feature set.


### -field CommandSetActive.BigLba

Indicates when <b>TRUE</b> that the device supports the 48-bit address feature set.


### -field CommandSetActive.DeviceConfigOverlay

 


### -field CommandSetActive.FlushCache

 


### -field CommandSetActive.FlushCacheExt

 


### -field CommandSetActive.Resrved3

Reserved.


### -field CommandSetActive.Words119_120Valid

 


### -field CommandSetActive.SmartErrorLog

 


### -field CommandSetActive.SmartSelfTest

 


### -field CommandSetActive.MediaSerialNumber

 


### -field CommandSetActive.MediaCardPassThrough

 


### -field CommandSetActive.StreamingFeature

 


### -field CommandSetActive.GpLogging

 


### -field CommandSetActive.WriteFua

 


### -field CommandSetActive.WriteQueuedFua

 


### -field CommandSetActive.WWN64Bit

 


### -field CommandSetActive.URGReadStream

 


### -field CommandSetActive.URGWriteStream

 


### -field CommandSetActive.ReservedForTechReport

 


### -field CommandSetActive.IdleWithUnloadFeature

 


### -field CommandSetActive.Reserved4

 


### -field NormalSecurityEraseUnit

 


### -field NormalSecurityEraseUnit.TimeRequired

 


### -field NormalSecurityEraseUnit.ExtendedTimeReported

 


### -field EnhancedSecurityEraseUnit

 


### -field EnhancedSecurityEraseUnit.TimeRequired

 


### -field EnhancedSecurityEraseUnit.ExtendedTimeReported

 


### -field PhysicalLogicalSectorSize



### -field PhysicalLogicalSectorSize.LogicalSectorsPerPhysicalSector

 


### -field PhysicalLogicalSectorSize.Reserved0

 


### -field PhysicalLogicalSectorSize.LogicalSectorLongerThan256Words

 


### -field PhysicalLogicalSectorSize.MultipleLogicalSectorsPerPhysicalSector

 


### -field PhysicalLogicalSectorSize.Reserved1

Reserved.


### -field CommandSetSupportExt



#### Reserved1

Reserved.


### -field CommandSetSupportExt.ReservedForDrqTechnicalReport

 


### -field CommandSetSupportExt.WriteReadVerify

 


### -field CommandSetSupportExt.WriteUncorrectableExt

 


### -field CommandSetSupportExt.ReadWriteLogDmaExt

 


### -field CommandSetSupportExt.DownloadMicrocodeMode3

 


### -field CommandSetSupportExt.FreefallControl

 


### -field CommandSetSupportExt.SenseDataReporting

 


### -field CommandSetSupportExt.ExtendedPowerConditions

 


### -field CommandSetSupportExt.Reserved0

 


### -field CommandSetSupportExt.WordValid

 


### -field CommandSetActiveExt



### -field CommandSetActiveExt.ReservedForDrqTechnicalReport

 


### -field CommandSetActiveExt.WriteReadVerify

 


### -field CommandSetActiveExt.WriteUncorrectableExt

 


### -field CommandSetActiveExt.ReadWriteLogDmaExt

 


### -field CommandSetActiveExt.DownloadMicrocodeMode3

 


### -field CommandSetActiveExt.FreefallControl

 


### -field CommandSetActiveExt.SenseDataReporting

 


### -field CommandSetActiveExt.ExtendedPowerConditions

 


### -field CommandSetActiveExt.Reserved0

 


### -field CommandSetActiveExt.Reserved1

Reserved.


### -field SecurityStatus

Contains a bitmap that indicates the security status. For more information about the meaning of each individual bit, see the <i>ATA/ATAPI specification</i>.


### -field SecurityStatus.SecuritySupported

 


### -field SecurityStatus.SecurityEnabled

 


### -field SecurityStatus.SecurityLocked

 


### -field SecurityStatus.SecurityFrozen

 


### -field SecurityStatus.SecurityCountExpired

 


### -field SecurityStatus.EnhancedSecurityEraseSupported

 


### -field SecurityStatus.Reserved0

 


### -field SecurityStatus.SecurityLevel

 


### -field SecurityStatus.Reserved1

Reserved.


### -field CfaPowerMode1

 


### -field CfaPowerMode1.MaximumCurrentInMA

 


### -field CfaPowerMode1.CfaPowerMode1Disabled

 


### -field CfaPowerMode1.CfaPowerMode1Required

 


### -field CfaPowerMode1.Reserved0

 


### -field CfaPowerMode1.Word160Supported

 


### -field DataSetManagementFeature



### -field DataSetManagementFeature.SupportsTrim

 


### -field DataSetManagementFeature.Reserved0

 


### -field SCTCommandTransport

 


### -field SCTCommandTransport.Supported

 


### -field SCTCommandTransport.Reserved0

 


### -field SCTCommandTransport.WriteSameSuported

 


### -field SCTCommandTransport.ErrorRecoveryControlSupported

 


### -field SCTCommandTransport.FeatureControlSuported

 


### -field SCTCommandTransport.DataTablesSuported

 


### -field SCTCommandTransport.Reserved1

 


### -field SCTCommandTransport.VendorSpecific

 


### -field BlockAlignment



### -field BlockAlignment.AlignmentOfLogicalWithinPhysical

 


### -field BlockAlignment.Word209Supported

 


### -field BlockAlignment.Reserved0

 


### -field NVCacheCapabilities



### -field NVCacheCapabilities.NVCachePowerModeEnabled

 


### -field NVCacheCapabilities.Reserved0

 


### -field NVCacheCapabilities.NVCacheFeatureSetEnabled

 


### -field NVCacheCapabilities.Reserved1

Reserved.


### -field NVCacheCapabilities.NVCachePowerModeVersion

 


### -field NVCacheCapabilities.NVCacheFeatureSetVersion

 


### -field NVCacheOptions



### -field NVCacheOptions.NVCacheEstimatedTimeToSpinUpInSeconds

 


### -field NVCacheOptions.Reserved

 


### -field TransportMajorVersion

 


### -field TransportMajorVersion.MajorVersion

 


### -field TransportMajorVersion.TransportType

 


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


### -field ReservedWords70

 


### -field QueueDepth

Indicates the maximum queue depth.


### -field ReservedWord75

Reserved.


### -field MajorRevision

Indicates the device's major revision number.


### -field MinorRevision

Indicates the device's minor revision number.


### -field UltraDMASupport

Contains a bitmap indicating which ultraDMA modes the device supports.


### -field UltraDMAActive

Contains a bitmap indicating which ultraDMA modes are selected.


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

 


### -field InterSeekDelay



### -field WorldWideName



### -field ReservedForWorldWideName128



### -field ReservedForTlcTechnicalReport



### -field WordsPerLogicalSector



### -field ReservedForExpandedSupportandActive



### -field MsnSupport

Indicates when <b>TRUE</b> that the device supports media status notification.


### -field ReservedWord127

 


### -field ReservedWord129

Reserved.


### -field ReservedForCfaWord161

Words 161-168


### -field NominalFormFactor

 


### -field ReservedWord168

 


### -field AdditionalProductID

 


### -field ReservedForCfaWord174

 


### -field CurrentMediaSerialNumber

Words 176-205


### -field ReservedWord207

Words 207-208


### -field WriteReadVerifySectorCountMode3Only

Words 210-211


### -field WriteReadVerifySectorCountMode2Only

Words 212-213


### -field NVCacheSizeLSW



### -field NVCacheSizeMSW



### -field NominalMediaRotationRate



### -field ReservedWord218



### -field WriteReadVerifySectorCountMode

 


### -field ReservedWord220

Words 220-254


### -field ReservedWord221

 


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

