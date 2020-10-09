---
UID: NE:ntddmmc._FEATURE_NUMBER
title: _FEATURE_NUMBER (ntddmmc.h)
description: The FEATURE_NUMBER enumeration provides a list of the features that are defined by the SCSI Multimedia - 4 (MMC-4) specification.
old-location: storage\feature_number.htm
tech.root: storage
ms.assetid: f139da57-1527-476d-8e9f-0b96876adecf
ms.date: 03/29/2018
keywords: ["FEATURE_NUMBER enumeration"]
ms.keywords: "*PFEATURE_NUMBER, FEATURE_NUMBER, FEATURE_NUMBER enumeration [Storage Devices], FeatureAACS, FeatureBDRPseudoOverwrite, FeatureBDRead, FeatureBDWrite, FeatureCDAudioAnalogPlay, FeatureCDRWMediaWriteSupport, FeatureCdMastering, FeatureCdRead, FeatureCdTrackAtOnce, FeatureCdrwCAVWrite, FeatureCore, FeatureDDCDRWWrite, FeatureDDCDRWrite, FeatureDDCDRead, FeatureDefectManagement, FeatureDiscControlBlocks, FeatureDvdCPRM, FeatureDvdCSS, FeatureDvdPlusR, FeatureDvdPlusRDualLayer, FeatureDvdPlusRW, FeatureDvdPlusRWDualLayer, FeatureDvdRead, FeatureDvdRecordableWrite, FeatureEmbeddedChanger, FeatureEnhancedDefectReporting, FeatureFirmwareDate, FeatureFormattable, FeatureHDDVDRead, FeatureHDDVDWrite, FeatureHybridDisc, FeatureIncrementalStreamingWritable, FeatureLayerJumpRecording, FeatureLogicalUnitSerialNumber, FeatureMediaSerialNumber, FeatureMicrocodeUpgrade, FeatureMorphing, FeatureMrw, FeatureMultiRead, FeaturePowerManagement, FeatureProfileList, FeatureRandomReadable, FeatureRandomWritable, FeatureRealTimeStreaming, FeatureRemovableMedium, FeatureRestrictedOverwrite, FeatureRigidRestrictedOverwrite, FeatureSMART, FeatureSectorErasable, FeatureTSR, FeatureTimeout, FeatureVCPS, FeatureWriteOnce, FeatureWriteProtect, PFEATURE_NUMBER, PFEATURE_NUMBER enumeration pointer [Storage Devices], _FEATURE_NUMBER, ntddmmc/FEATURE_NUMBER, ntddmmc/FeatureAACS, ntddmmc/FeatureBDRPseudoOverwrite, ntddmmc/FeatureBDRead, ntddmmc/FeatureBDWrite, ntddmmc/FeatureCDAudioAnalogPlay, ntddmmc/FeatureCDRWMediaWriteSupport, ntddmmc/FeatureCdMastering, ntddmmc/FeatureCdRead, ntddmmc/FeatureCdTrackAtOnce, ntddmmc/FeatureCdrwCAVWrite, ntddmmc/FeatureCore, ntddmmc/FeatureDDCDRWWrite, ntddmmc/FeatureDDCDRWrite, ntddmmc/FeatureDDCDRead, ntddmmc/FeatureDefectManagement, ntddmmc/FeatureDiscControlBlocks, ntddmmc/FeatureDvdCPRM, ntddmmc/FeatureDvdCSS, ntddmmc/FeatureDvdPlusR, ntddmmc/FeatureDvdPlusRDualLayer, ntddmmc/FeatureDvdPlusRW, ntddmmc/FeatureDvdPlusRWDualLayer, ntddmmc/FeatureDvdRead, ntddmmc/FeatureDvdRecordableWrite, ntddmmc/FeatureEmbeddedChanger, ntddmmc/FeatureEnhancedDefectReporting, ntddmmc/FeatureFirmwareDate, ntddmmc/FeatureFormattable, ntddmmc/FeatureHDDVDRead, ntddmmc/FeatureHDDVDWrite, ntddmmc/FeatureHybridDisc, ntddmmc/FeatureIncrementalStreamingWritable, ntddmmc/FeatureLayerJumpRecording, ntddmmc/FeatureLogicalUnitSerialNumber, ntddmmc/FeatureMediaSerialNumber, ntddmmc/FeatureMicrocodeUpgrade, ntddmmc/FeatureMorphing, ntddmmc/FeatureMrw, ntddmmc/FeatureMultiRead, ntddmmc/FeaturePowerManagement, ntddmmc/FeatureProfileList, ntddmmc/FeatureRandomReadable, ntddmmc/FeatureRandomWritable, ntddmmc/FeatureRealTimeStreaming, ntddmmc/FeatureRemovableMedium, ntddmmc/FeatureRestrictedOverwrite, ntddmmc/FeatureRigidRestrictedOverwrite, ntddmmc/FeatureSMART, ntddmmc/FeatureSectorErasable, ntddmmc/FeatureTSR, ntddmmc/FeatureTimeout, ntddmmc/FeatureVCPS, ntddmmc/FeatureWriteOnce, ntddmmc/FeatureWriteProtect, ntddmmc/PFEATURE_NUMBER, storage.feature_number, structs-CD-ROM_6d75ed9b-8d13-4715-ae9a-51bc2a6025f0.xml"
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
req.irql: 
targetos: Windows
req.typenames: FEATURE_NUMBER, *PFEATURE_NUMBER
f1_keywords:
 - _FEATURE_NUMBER
 - ntddmmc/_FEATURE_NUMBER
 - PFEATURE_NUMBER
 - ntddmmc/PFEATURE_NUMBER
 - FEATURE_NUMBER
 - ntddmmc/FEATURE_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_NUMBER
---

# _FEATURE_NUMBER enumeration


## -description

The FEATURE_NUMBER enumeration provides a list of the features that are defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

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

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>