---
UID: NE:ntddmmc._FEATURE_NUMBER
title: "_FEATURE_NUMBER"
author: windows-driver-content
description: The FEATURE_NUMBER enumeration provides a list of the features that are defined by the SCSI Multimedia - 4 (MMC-4) specification.
old-location: storage\feature_number.htm
old-project: storage
ms.assetid: f139da57-1527-476d-8e9f-0b96876adecf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: FeatureMicrocodeUpgrade, ntddmmc/FeatureCdrwCAVWrite, FeatureDvdCSS, ntddmmc/FeatureDvdCSS, ntddmmc/FeatureRemovableMedium, FeatureFirmwareDate, ntddmmc/FeatureRigidRestrictedOverwrite, ntddmmc/FeatureAACS, FeatureAACS, ntddmmc/FeatureDDCDRWWrite, ntddmmc/FeatureRandomWritable, ntddmmc/FeatureCdRead, FeaturePowerManagement, ntddmmc/FeatureDefectManagement, ntddmmc/FeatureHDDVDRead, FEATURE_NUMBER, FeatureLayerJumpRecording, PFEATURE_NUMBER enumeration pointer [Storage Devices], ntddmmc/FeatureCDRWMediaWriteSupport, ntddmmc/FeaturePowerManagement, ntddmmc/FeatureBDWrite, ntddmmc/FeatureMrw, FeatureCdRead, FeatureRemovableMedium, ntddmmc/FeatureDiscControlBlocks, ntddmmc/FeatureDvdCPRM, FeatureVCPS, ntddmmc/FeatureFirmwareDate, FeatureMrw, ntddmmc/FeatureBDRead, FEATURE_NUMBER enumeration [Storage Devices], ntddmmc/FeatureSMART, structs-CD-ROM_6d75ed9b-8d13-4715-ae9a-51bc2a6025f0.xml, ntddmmc/FeatureDvdPlusRDualLayer, ntddmmc/FeatureCore, FeatureWriteProtect, ntddmmc/FeatureCdMastering, ntddmmc/PFEATURE_NUMBER, FeatureDvdPlusRWDualLayer, ntddmmc/FeatureTSR, FeatureSectorErasable, FeatureHybridDisc, storage.feature_number, ntddmmc/FeatureDvdPlusRWDualLayer, ntddmmc/FeatureMicrocodeUpgrade, FeatureCore, ntddmmc/FeatureRestrictedOverwrite, ntddmmc/FeatureEnhancedDefectReporting, ntddmmc/FeatureHDDVDWrite, FeatureMorphing, *PFEATURE_NUMBER, FeatureWriteOnce, ntddmmc/FeatureFormattable, FeatureDDCDRWrite, FeatureRealTimeStreaming, ntddmmc/FeatureDvdPlusRW, FeatureDvdRead, FeatureIncrementalStreamingWritable, FeatureDefectManagement, FeatureRestrictedOverwrite, FeatureEnhancedDefectReporting, ntddmmc/FeatureDDCDRead, _FEATURE_NUMBER, FeatureLogicalUnitSerialNumber, FeatureSMART, FeatureMediaSerialNumber, ntddmmc/FeatureIncrementalStreamingWritable, FeatureDvdCPRM, ntddmmc/FeatureLayerJumpRecording, ntddmmc/FeatureEmbeddedChanger, ntddmmc/FeatureDvdRecordableWrite, ntddmmc/FeatureMediaSerialNumber, ntddmmc/FeatureTimeout, ntddmmc/FeatureDvdRead, FeatureDDCDRWWrite, FeatureCDAudioAnalogPlay, FeatureDvdPlusRW, FeatureCdMastering, FeatureMultiRead, FeatureEmbeddedChanger, ntddmmc/FeatureLogicalUnitSerialNumber, ntddmmc/FeatureMorphing, ntddmmc/FeatureDDCDRWrite, FeatureBDRPseudoOverwrite, ntddmmc/FeatureRandomReadable, ntddmmc/FeatureCdTrackAtOnce, FeatureProfileList, FeatureCdTrackAtOnce, PFEATURE_NUMBER, FeatureTSR, ntddmmc/FeatureHybridDisc, FeatureRigidRestrictedOverwrite, ntddmmc/FeatureRealTimeStreaming, ntddmmc/FeatureSectorErasable, FeatureBDRead, FeatureDvdPlusRDualLayer, ntddmmc/FeatureWriteProtect, FeatureTimeout, FeatureFormattable, FeatureCdrwCAVWrite, ntddmmc/FEATURE_NUMBER, ntddmmc/FeatureProfileList, FeatureCDRWMediaWriteSupport, FeatureRandomWritable, ntddmmc/FeatureWriteOnce, ntddmmc/FeatureVCPS, FeatureDvdRecordableWrite, FeatureDvdPlusR, ntddmmc/FeatureMultiRead, ntddmmc/FeatureBDRPseudoOverwrite, FeatureDiscControlBlocks, FeatureRandomReadable, ntddmmc/FeatureDvdPlusR, FeatureHDDVDWrite, ntddmmc/FeatureCDAudioAnalogPlay, FeatureDDCDRead, FeatureBDWrite, FeatureHDDVDRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_NUMBER
product: Windows
targetos: Windows
req.typenames: FEATURE_NUMBER, *PFEATURE_NUMBER
---

# _FEATURE_NUMBER enumeration


## -description


The FEATURE_NUMBER enumeration provides a list of the features that are defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. 


## -syntax


````
typedef enum _FEATURE_NUMBER { 
  FeatureProfileList                   = 0x0000,
  FeatureCore                          = 0x0001,
  FeatureMorphing                      = 0x0002,
  FeatureRemovableMedium               = 0x0003,
  FeatureWriteProtect                  = 0x0004,
  FeatureRandomReadable                = 0x0010,
  FeatureMultiRead                     = 0x001D,
  FeatureCdRead                        = 0x001E,
  FeatureDvdRead                       = 0x001F,
  FeatureRandomWritable                = 0x0020,
  FeatureIncrementalStreamingWritable  = 0x0021,
  FeatureSectorErasable                = 0x0022,
  FeatureFormattable                   = 0x0023,
  FeatureDefectManagement              = 0x0024,
  FeatureWriteOnce                     = 0x0025,
  FeatureRestrictedOverwrite           = 0x0026,
  FeatureCdrwCAVWrite                  = 0x0027,
  FeatureMrw                           = 0x0028,
  FeatureEnhancedDefectReporting       = 0x0029,
  FeatureDvdPlusRW                     = 0x002A,
  FeatureDvdPlusR                      = 0x002B,
  FeatureRigidRestrictedOverwrite      = 0x002C,
  FeatureCdTrackAtOnce                 = 0x002D,
  FeatureCdMastering                   = 0x002E,
  FeatureDvdRecordableWrite            = 0x002F,
  FeatureDDCDRead                      = 0x0030,
  FeatureDDCDRWrite                    = 0x0031,
  FeatureDDCDRWWrite                   = 0x0032,
  FeatureLayerJumpRecording            = 0x0033,
  FeatureCDRWMediaWriteSupport         = 0x0037,
  FeatureBDRPseudoOverwrite            = 0x0038,
  FeatureDvdPlusRWDualLayer            = 0x003A,
  FeatureDvdPlusRDualLayer             = 0x003B,
  FeatureBDRead                        = 0x0040,
  FeatureBDWrite                       = 0x0041,
  FeatureTSR                           = 0x0042,
  FeatureHDDVDRead                     = 0x0050,
  FeatureHDDVDWrite                    = 0x0051,
  FeatureHybridDisc                    = 0x0080,
  FeaturePowerManagement               = 0x0100,
  FeatureSMART                         = 0x0101,
  FeatureEmbeddedChanger               = 0x0102,
  FeatureCDAudioAnalogPlay             = 0x0103,
  FeatureMicrocodeUpgrade              = 0x0104,
  FeatureTimeout                       = 0x0105,
  FeatureDvdCSS                        = 0x0106,
  FeatureRealTimeStreaming             = 0x0107,
  FeatureLogicalUnitSerialNumber       = 0x0108,
  FeatureMediaSerialNumber             = 0x0109,
  FeatureDiscControlBlocks             = 0x010A,
  FeatureDvdCPRM                       = 0x010B,
  FeatureFirmwareDate                  = 0x010C,
  FeatureAACS                          = 0x010D,
  FeatureVCPS                          = 0x0110
} FEATURE_NUMBER, *PFEATURE_NUMBER;
````


## -enum-fields




### -field FeatureProfileList

Indicates the feature named "Profile List" by the <i>MMC-3 </i>specification. This feature provides a list of all profiles supported by the device. 


### -field FeatureCore

Indicates the feature named "Core" by the <i>MMC-3 </i>specification. This feature encompasses the basic functionality which is mandatory for all devices that support the <i>MMC-3</i> standard. See the <i>MMC-3</i> specification for a description of the capabilities included in the Core feature. 


### -field FeatureMorphing

Indicates the feature named "Morphing" by the <i>MMC-3 </i>specification. Devices that support this feature can notify the initiator of operational changes and allow the initiator to prevent operational changes. 


### -field FeatureRemovableMedium

Indicates the feature named "Removable Medium" by the <i>MMC-3 </i>specification. Devices that support this feature allow the medium to be removed from the device. They also can communicate to the initiator that the user wants to eject the medium or has inserted a new medium. 


### -field FeatureWriteProtect

Indicates the feature named "Write Protect" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to change the write-protection state of the media programmatically. 


### -field FeatureRandomReadable

Indicates the feature named "Random Readable" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to read blocks of data on the disk at random locations. These devices do not require that the initiator address disk locations in any particular order. 


### -field FeatureMultiRead

Indicates the feature named "MultiRead," originally defined by the Optical Storage Technology Association (OSTA) and incorporated into the <i>MMC-3 </i>specification. Devices that support this feature can read all CD media types. 


### -field FeatureCdRead

Indicates the feature named "CD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read CD-specific information from the media and can read user data from all types of CD blocks. 


### -field FeatureDvdRead

Indicates the feature named "DVD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read DVD-specific information from the media.


### -field FeatureRandomWritable

Indicates the feature named "Random Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can write blocks of data to random locations on the disk. These devices do not require that the initiator address disk locations in any particular order. 


### -field FeatureIncrementalStreamingWritable

Indicates the feature named "Incremental Streaming Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can append data to a limited number of locations on the media. 


### -field FeatureSectorErasable

Indicates the feature named "Sector Erasable" by the <i>MMC-3 </i>specification. Devices that support this feature require an erase pass before overwriting existing data.


### -field FeatureFormattable

Indicates the feature named "Formattable" by the <i>MMC-3 </i>specification. Devices that support this feature can format media into logical blocks. 


### -field FeatureDefectManagement

Indicates the feature named "Defect Management" by the <i>MMC-3 </i>specification. Devices that support this feature are able to provide contiguous address space that is guaranteed to be defect free. 


### -field FeatureWriteOnce

Indicates the feature named "Write Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write to any previously unused logical block. 


### -field FeatureRestrictedOverwrite

Indicates the feature named "Restricted Overwrite" by the <i>MMC-3 </i>specification. Devices that support this feature are limited in regard to which logical blocks they can overwrite at any given time. 


### -field FeatureCdrwCAVWrite

Indicates the feature named "CD-RW CAV Write" by the <i>MMC-3 </i>specification. Devices that support this feature can perform writes on CD-RW media in CAV mode. 


### -field FeatureMrw

Indicates the feature named "MRW" by the <i>MMC-3 </i>specification. Devices that support this feature can recognize, read and optionally write MRW formatted media. 


### -field FeatureEnhancedDefectReporting



### -field FeatureDvdPlusRW

Indicates the feature named "DVD+RW" by the <i>MMC-3 </i>specification. Devices that support this feature can recognize, read and optionally write DVD+RW media. 


### -field FeatureDvdPlusR



### -field FeatureRigidRestrictedOverwrite

Indicates the feature named "DVD-RW Restricted Overwrite" by the <i>MMC-3 </i>specification. Devices that support this feature can only write on block boundaries. These devices cannot perform read or write operations that transfer less than a block of data. 


### -field FeatureCdTrackAtOnce

Indicates the feature named "CD Track at Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a CD track. 


### -field FeatureCdMastering

Indicates the feature named "CD Mastering" by the <i>MMC-3 </i>specification. Devices that support this feature can write to a CD in either "Session-at-Once" mode or raw mode. 


### -field FeatureDvdRecordableWrite

Indicates the feature named "DVD-R Write" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a write-once DVD media in "Disc-at-Once" mode.


### -field FeatureDDCDRead

Indicates the feature named "DDCD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read user data from DDCD blocks. 


### -field FeatureDDCDRWrite

Indicates the feature named "DDCD-R Write" by the <i>MMC-3 </i>specification. Devices that support this feature can read and write DDCD-R media. 


### -field FeatureDDCDRWWrite

Indicates the feature named "DDCD-RW Write" by the <i>MMC-3 </i>specification. Devices that support this feature can read and write DDCD-RW media. 


### -field FeatureLayerJumpRecording

Reserved 0x0034 - 0x0036


### -field FeatureCDRWMediaWriteSupport



### -field FeatureBDRPseudoOverwrite

Reserved 0x0039


### -field FeatureDvdPlusRWDualLayer



### -field FeatureDvdPlusRDualLayer

Reserved 0x003c - 0x003f


### -field FeatureBDRead



### -field FeatureBDWrite



### -field FeatureTSR

Reserved 0x0043 - 0x004f


### -field FeatureHDDVDRead



### -field FeatureHDDVDWrite

Reserved 0x0052 - 0x007f


### -field FeatureHybridDisc

Reserved 0x0081 - 0x00ff


### -field FeaturePowerManagement

Indicates the feature named "Power Management" by the <i>MMC-3 </i>specification. Devices that support this feature can perform both initiator and logical-unit directed power management. 


### -field FeatureSMART

Indicates the feature named "S.M.A.R.T." by the <i>MMC-3 </i>specification. Devices that support this feature support Self-Monitoring Analysis and Reporting Technology (SMART). 


### -field FeatureEmbeddedChanger

Indicates the feature named "Embedded Changer" by the <i>MMC-3 </i>specification. Devices that support this feature can move media back and forth between a media storage area and the mechanism that actually accesses the media. 


### -field FeatureCDAudioAnalogPlay

Indicates the feature named "CD Audio External Play" by the <i>MMC-3 </i>specification. Devices that support this feature can play CD audio data and channel it directly to an external output. 


### -field FeatureMicrocodeUpgrade

Indicates the feature named "Microcode Upgrade" by the <i>MMC-3 </i>specification. Devices that support this feature can upgrade their internal microcode by means of a published interface. 


### -field FeatureTimeout

Indicates the feature named "Time-Out" by the <i>MMC-3 </i>specification. Devices that have this feature must respond to commands within a set time period. When these devices cannot complete commands in the allotted time, they complete the commands with an error. 


### -field FeatureDvdCSS

Indicates the feature named "DVD-CSS" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Scrambling System (DVD-CSS) authentication and key management. 


### -field FeatureRealTimeStreaming

Indicates the feature named "Real Time Streaming" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to specify the performance level of the device within certain limits allowed by the device. These devices must also indicate to the initiator whether they support stream playback operations. 


### -field FeatureLogicalUnitSerialNumber

Indicates the feature named "Device Serial Number" by the <i>MMC-3 </i>specification. Devices that support this feature can furnish the initiator with a serial number that uniquely identifies the device. 


### -field FeatureMediaSerialNumber



### -field FeatureDiscControlBlocks

Indicates the feature named "Disc Control Blocks" by the <i>MMC-3 </i>specification. Devices that support this feature can read or write Disc Control Blocks. 


### -field FeatureDvdCPRM

Indicates the feature named "DVD CPRM" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Protection for Recordable Media (CPRM) authentication and key management. 


### -field FeatureFirmwareDate



### -field FeatureAACS

Reserved 0x010e - 0x010f


### -field FeatureVCPS

Reserved 0x0111 - 0xfeff


## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_NUMBER enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

