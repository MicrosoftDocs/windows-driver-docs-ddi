---
UID: NS:ntddmmc._FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
title: "_FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE"
author: windows-driver-content
description: The FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure contains information for the Restricted Overwrite feature.
old-location: storage\feature_data_dvd_rw_restricted_overwrite.htm
old-project: storage
ms.assetid: 1669872a-4306-4773-bd7e-6f481c5e689d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure [Storage Devices], PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure pointer [Storage Devices], _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, ntddmmc/FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, ntddmmc/PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, storage.feature_data_dvd_rw_restricted_overwrite, structs-CD-ROM_b6d53c83-8d7d-4fc1-9e42-b173219961a4.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, *PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
---

# _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure


## -description


The FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure contains information for the Restricted Overwrite feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Blank

Indicates, when set to 1, that the device supports the BLANK command defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification, with Blanking Types of zero and one. When set to zero, this bit indicates that the device does not support this command. 


### -field Intermediate

Indicates, when set to 1, that the device supports writing on an intermediate state-bordered area and quick formatting (Format Type of 15 - Quick Format, as defined by the <i>MMC-3</i> specification). When set to zero, this bit indicates that the device does not support writing on an intermediate state-bordered area nor does it support quick formatting. 


### -field DefectStatusDataRead

Corresponds to the Defect Status Bitmap Read (DSBR) bit as defined by the <i>MMC-3</i> specification. When set to 1, this bit indicates that the device allows initiators to read the Defect Status Bitmap of a medium. When set to zero, this bit indicates that the device does not support the reading of Defect Status Bitmap. 


### -field DefectStatusDataGenerate

Corresponds to the Defect Status Bitmap Generate (DSBG) bit as defined by the <i>MMC-3</i> specification. When set to 1, this bit indicates that the device can generate a Defect Status Bitmap during formatting. When set to zero, this bit indicates that the device cannot generate a Defect Status Bitmap during formatting. 


### -field Reserved0

Reserved. 


### -field Reserved1

Reserved. 


## -remarks



This structure holds data for the feature named "DVD-RW Restricted Overwrite" by the <i>MMC-3 </i>specification. In the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a> enumeration, this feature is named <b>FeatureRigidRestrictedOverwrite</b>.

Devices that support this feature can only write on block boundaries. These devices cannot perform read or write operations that transfer less than a block of data. See the <i>MMC-3</i> specification for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

