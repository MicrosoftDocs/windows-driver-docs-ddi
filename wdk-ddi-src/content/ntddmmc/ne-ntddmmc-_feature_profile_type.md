---
UID: NE:ntddmmc._FEATURE_PROFILE_TYPE
title: _FEATURE_PROFILE_TYPE (ntddmmc.h)
description: The FEATURE_PROFILE_TYPE enumeration provides a list of the profile names that are defined by the SCSI Multimedia - 4 (MMC-4) specification.
old-location: storage\feature_profile_type.htm
tech.root: storage
ms.assetid: 60cce78f-1025-41a7-861d-150ef28376cb
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_PROFILE_TYPE, FEATURE_PROFILE_TYPE, FEATURE_PROFILE_TYPE enumeration [Storage Devices], PFEATURE_PROFILE_TYPE, PFEATURE_PROFILE_TYPE enumeration pointer [Storage Devices], ProfileAS_MO, ProfileBDRRandomWritable, ProfileBDRSequentialWritable, ProfileBDRewritable, ProfileBDRom, ProfileCdRecordable, ProfileCdRewritable, ProfileCdrom, ProfileDDCdRecordable, ProfileDDCdRewritable, ProfileDDCdrom, ProfileDvdDashRDualLayer, ProfileDvdDashRLayerJump, ProfileDvdPlusR, ProfileDvdPlusRDualLayer, ProfileDvdPlusRW, ProfileDvdPlusRWDualLayer, ProfileDvdRWSequential, ProfileDvdRam, ProfileDvdRecordable, ProfileDvdRewritable, ProfileDvdRom, ProfileHDDVDRDualLayer, ProfileHDDVDRWDualLayer, ProfileHDDVDRam, ProfileHDDVDRecordable, ProfileHDDVDRewritable, ProfileHDDVDRom, ProfileInvalid, ProfileMOErasable, ProfileMOWriteOnce, ProfileNonRemovableDisk, ProfileNonStandard, ProfileRemovableDisk, _FEATURE_PROFILE_TYPE, ntddmmc/FEATURE_PROFILE_TYPE, ntddmmc/PFEATURE_PROFILE_TYPE, ntddmmc/ProfileAS_MO, ntddmmc/ProfileBDRRandomWritable, ntddmmc/ProfileBDRSequentialWritable, ntddmmc/ProfileBDRewritable, ntddmmc/ProfileBDRom, ntddmmc/ProfileCdRecordable, ntddmmc/ProfileCdRewritable, ntddmmc/ProfileCdrom, ntddmmc/ProfileDDCdRecordable, ntddmmc/ProfileDDCdRewritable, ntddmmc/ProfileDDCdrom, ntddmmc/ProfileDvdDashRDualLayer, ntddmmc/ProfileDvdDashRLayerJump, ntddmmc/ProfileDvdPlusR, ntddmmc/ProfileDvdPlusRDualLayer, ntddmmc/ProfileDvdPlusRW, ntddmmc/ProfileDvdPlusRWDualLayer, ntddmmc/ProfileDvdRWSequential, ntddmmc/ProfileDvdRam, ntddmmc/ProfileDvdRecordable, ntddmmc/ProfileDvdRewritable, ntddmmc/ProfileDvdRom, ntddmmc/ProfileHDDVDRDualLayer, ntddmmc/ProfileHDDVDRWDualLayer, ntddmmc/ProfileHDDVDRam, ntddmmc/ProfileHDDVDRecordable, ntddmmc/ProfileHDDVDRewritable, ntddmmc/ProfileHDDVDRom, ntddmmc/ProfileInvalid, ntddmmc/ProfileMOErasable, ntddmmc/ProfileMOWriteOnce, ntddmmc/ProfileNonRemovableDisk, ntddmmc/ProfileNonStandard, ntddmmc/ProfileRemovableDisk, storage.feature_profile_type, structs-CD-ROM_89bf20da-a096-4f37-ab24-219533578d34.xml"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddmmc.h
api_name:
- FEATURE_PROFILE_TYPE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_PROFILE_TYPE, *PFEATURE_PROFILE_TYPE
---

# _FEATURE_PROFILE_TYPE enumeration


## -description


The FEATURE_PROFILE_TYPE enumeration provides a list of the profile names that are defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. 


## -enum-fields




### -field ProfileInvalid

Does not indicate a valid profile. 


### -field ProfileNonRemovableDisk

Indicates the profile named "Nonremovable disk" by the <i>SCSI-3 Multimedia (MMC-3)</i> specification. This profile is used with devices that manage rewritable media and are capable of changing behavior. 


### -field ProfileRemovableDisk

Indicates the profile named "Removable disk" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable, removable media. 


### -field ProfileMOErasable

Indicates the profile named "MO Erasable" by the <i>MMC-3</i> specification. This profile is used with devices that manage magneto-optical media and that have a sector-erase capability. 


### -field ProfileMOWriteOnce

Indicates the profile named "MO Write Once" by the <i>MMC-3</i> specification. This profile is used with devices that manage magneto-optical write-once media.


### -field ProfileAS_MO

Indicates the profile named "AS-MO" by the <i>MMC-3</i> specification. This profile is used with devices that implement Advance Storage technology and manage magneto-optical media. 


### -field ProfileCdrom

Indicates the profile named "CD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that manage read-only compact disc media.


### -field ProfileCdRecordable

Indicates the profile named "CD-R" by the <i>MMC-3</i> specification. This profile is used with devices that manage write-once compact disc media. 


### -field ProfileCdRewritable

Indicates the profile named "CD-RW" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable compact disc media. 


### -field ProfileDvdRom

Indicates the profile named "DVD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that manage read-only DVD media. 


### -field ProfileDvdRecordable

Indicates the profile named "DVD-R" by the <i>MMC-3</i> specification. This profile is used with devices that manage write-once DVD media and operate in sequential recording mode. 


### -field ProfileDvdRam

Indicates the profile named "DVD-RAM or DVD+RW" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable DVD media. 


### -field ProfileDvdRewritable

Indicates the profile named "DVD-RW Restricted Overwrite" by the <i>MMC-3</i> specification. This profile is used with devices that manage rerecordable DVD media and operate in packet-writing mode. 


### -field ProfileDvdRWSequential

Indicates the profile named "DVD-RW Sequential Recording" by the <i>MMC-3</i> specification. This profile is used with devices that implement a series of features associated with sequential recording, such as the features "Incremental Streaming Writable" and "Real-Time Streaming". For a full list of the features supported with this profile, see the <i>MMC-3</i> specification. 


### -field ProfileDvdDashRDualLayer


### -field ProfileDvdDashRLayerJump

Reserved 0x0017 - 0x0019


### -field ProfileDvdPlusRW

Indicates the profile named "DVD+RW" by the <i>MMC-3</i> specification. This profile is used with devices that implement a series of features required to manage DVD media that is both readable and writable. For a full list of the features supported with this profile, see the <i>MMC-3</i> specification. 


### -field ProfileDvdPlusR

Reserved 0x001C - 001F


### -field ProfileDDCdrom

Indicates the profile named "DDCD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification. 


### -field ProfileDDCdRecordable

Indicates the profile named "DDCD-R" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD-R specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification. 


### -field ProfileDDCdRewritable

Indicates the profile named "DDCD-RW" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD-RW specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification. 


### -field ProfileDvdPlusRWDualLayer


### -field ProfileDvdPlusRDualLayer

Reserved 0x002C - 0x003F


### -field ProfileBDRom


### -field ProfileBDRSequentialWritable

BD-R 'SRM'


### -field ProfileBDRRandomWritable

BD-R 'RRM'


### -field ProfileBDRewritable

Reserved 0x0044 - 0x004F


### -field ProfileHDDVDRom


### -field ProfileHDDVDRecordable


### -field ProfileHDDVDRam


### -field ProfileHDDVDRewritable

Reserved 0x0054 - 0x0057


### -field ProfileHDDVDRDualLayer

Reserved 0x0059 - 0x0059


### -field ProfileHDDVDRWDualLayer

Reserved 0x005B - 0xfffe


### -field ProfileNonStandard

Indicates that the device does not conform to any profile. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553816">FEATURE_DATA_PROFILE_LIST</a>
 

 

