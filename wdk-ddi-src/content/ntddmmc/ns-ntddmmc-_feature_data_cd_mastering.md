---
UID: NS:ntddmmc._FEATURE_DATA_CD_MASTERING
title: "_FEATURE_DATA_CD_MASTERING"
author: windows-driver-content
description: The FEATURE_DATA_CD_MASTERING structure holds information for the CD Mastering feature.
old-location: storage\feature_data_cd_mastering.htm
old-project: storage
ms.assetid: 340e9675-9d07-4224-ac1b-86e7586c0738
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_CD_MASTERING, FEATURE_DATA_CD_MASTERING, FEATURE_DATA_CD_MASTERING structure [Storage Devices], PFEATURE_DATA_CD_MASTERING, PFEATURE_DATA_CD_MASTERING structure pointer [Storage Devices], _FEATURE_DATA_CD_MASTERING, ntddmmc/FEATURE_DATA_CD_MASTERING, ntddmmc/PFEATURE_DATA_CD_MASTERING, storage.feature_data_cd_mastering, structs-CD-ROM_f803f10f-2ef7-4e3b-9c16-1ed2f3c5b2a5.xml"
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
-	FEATURE_DATA_CD_MASTERING
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_CD_MASTERING, *PFEATURE_DATA_CD_MASTERING
---

# _FEATURE_DATA_CD_MASTERING structure


## -description


The FEATURE_DATA_CD_MASTERING structure holds information for the CD Mastering feature.


## -syntax


````
typedef struct _FEATURE_DATA_CD_MASTERING {
  FEATURE_HEADER Header;
  UCHAR          RWSubchannelsRecordable  :1;
  UCHAR          CdRewritable  :1;
  UCHAR          TestWriteOk  :1;
  UCHAR          RawRecordingOk  :1;
  UCHAR          RawMultiSessionOk  :1;
  UCHAR          SessionAtOnceOk  :1;
  UCHAR          BufferUnderrunFree  :1;
  UCHAR          Reserved1  :1;
  UCHAR          MaximumCueSheetLength[3];
} FEATURE_DATA_CD_MASTERING, *PFEATURE_DATA_CD_MASTERING;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field RWSubchannelsRecordable

Indicates, when set to 1, that the device can record the R-W subchannels with user-supplied information. 


### -field CdRewritable

Indicates, when set to 1, that the device can do mastering and TAO recording on rewritable media. 


### -field TestWriteOk

Indicates, when set to 1, that the device can perform test writes. 


### -field RawRecordingOk

Indicates, when set to 1, that the device can record using the raw write type. 


### -field RawMultiSessionOk

Indicates, when set to 1, that the device can record multisession in raw mode. 


### -field SessionAtOnceOk

Indicates, when set to 1, that the device can record using the Session-at-Once recording mode. 


### -field BufferUnderrunFree

Indicates, when set to 1, that the device is capable of zero-loss linking.


### -field Reserved1

Reserved. 


### -field MaximumCueSheetLength

Indicates the maximum length of a Cue Sheet that can be accepted by the device for Session at Once recording. <b>MaximumCueSheetLength</b>[0] holds the most significant byte of the 3-byte value for the length. <b>MaximumCueSheetLength</b>[2] holds the least significant byte. 


## -remarks



This structure holds data for the feature named "CD Mastering" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can write to a CD in either "Session-at-Once" mode or Raw mode. 




## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CD_MASTERING structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

