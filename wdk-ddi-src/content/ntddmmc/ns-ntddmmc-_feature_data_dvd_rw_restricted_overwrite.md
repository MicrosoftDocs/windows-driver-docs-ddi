---
UID: NS:ntddmmc._FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
title: _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
author: windows-driver-content
description: The FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure contains information for the Restricted Overwrite feature.
old-location: storage\feature_data_dvd_rw_restricted_overwrite.htm
old-project: storage
ms.assetid: 1669872a-4306-4773-bd7e-6f481c5e689d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, *PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
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
req.alt-api: FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
req.alt-loc: ntddmmc.h
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
req.typenames: *PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE
---

# _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure



## -description
The FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure contains information for the Restricted Overwrite feature. 



## -syntax

````
typedef struct _FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE {
  FEATURE_HEADER Header;
  UCHAR          Blank  :1;
  UCHAR          Intermediate  :1;
  UCHAR          DefectStatusDataRead  :1;
  UCHAR          DefectStatusDataGenerate  :1;
  UCHAR          Reserved0  :4;
  UCHAR          Reserved1[3];
} FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE, *PFEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE;
````


## -struct-fields

### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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
This structure holds data for the feature named "DVD-RW Restricted Overwrite" by the <i>MMC-3 </i>specification. In the <a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a> enumeration, this feature is named <b>FeatureRigidRestrictedOverwrite</b>.

Devices that support this feature can only write on block boundaries. These devices cannot perform read or write operations that transfer less than a block of data. See the <i>MMC-3</i> specification for more information. 


## -see-also
<dl>
<dt>
<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>
</dt>
<dt>
<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_RW_RESTRICTED_OVERWRITE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

