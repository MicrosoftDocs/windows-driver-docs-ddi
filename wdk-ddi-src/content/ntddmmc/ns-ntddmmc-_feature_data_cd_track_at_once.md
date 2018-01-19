---
UID: NS:ntddmmc._FEATURE_DATA_CD_TRACK_AT_ONCE
title: _FEATURE_DATA_CD_TRACK_AT_ONCE
author: windows-driver-content
description: The FEATURE_DATA_CD_TRACK_AT_ONCE structure holds information about the CD Track at Once feature.
old-location: storage\feature_data_cd_track_at_once.htm
old-project: storage
ms.assetid: e3ce42a6-0d94-46cb-9831-c29f92a677cd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FEATURE_DATA_CD_TRACK_AT_ONCE, *PFEATURE_DATA_CD_TRACK_AT_ONCE, FEATURE_DATA_CD_TRACK_AT_ONCE
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
req.alt-api: FEATURE_DATA_CD_TRACK_AT_ONCE
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
req.typenames: *PFEATURE_DATA_CD_TRACK_AT_ONCE, FEATURE_DATA_CD_TRACK_AT_ONCE
---

# _FEATURE_DATA_CD_TRACK_AT_ONCE structure



## -description
The FEATURE_DATA_CD_TRACK_AT_ONCE structure holds information about the CD Track at Once feature. 



## -syntax

````
typedef struct _FEATURE_DATA_CD_TRACK_AT_ONCE {
  FEATURE_HEADER Header;
  UCHAR          RWSubchannelsRecordable  :1;
  UCHAR          CdRewritable  :1;
  UCHAR          TestWriteOk  :1;
  UCHAR          RWSubchannelPackedOk  :1;
  UCHAR          RWSubchannelRawOk  :1;
  UCHAR          Reserved1  :1;
  UCHAR          BufferUnderrunFree  :1;
  UCHAR          Reserved3  :1;
  UCHAR          Reserved2;
  UCHAR          DataTypeSupported[2];
} FEATURE_DATA_CD_TRACK_AT_ONCE, *PFEATURE_DATA_CD_TRACK_AT_ONCE;
````


## -struct-fields

### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.


### -field RWSubchannelsRecordable

Indicates, when set to 1, that the device can record the read/write subchannels with user-supplied data. 


### -field CdRewritable

Indicates, when set to 1, that the device supports overwriting a Track-at-Once track with another track's information. 


### -field TestWriteOk

Indicates, when set to 1, that the device can perform test writes. 


### -field RWSubchannelPackedOk

Indicates, when set to 1, that the device supports writing R-W sub code in the packed mode. 


### -field RWSubchannelRawOk

Indicates, when set to 1, that the device supports writing R-W sub code in the raw mode. 


### -field Reserved1

Reserved. 


### -field BufferUnderrunFree

Indicates, when set to 1, that the device is capable of zero-loss linking.


### -field Reserved3

Reserved. 


### -field Reserved2

Reserved. 


### -field DataTypeSupported

Indicates the data types that the device supports. See the <i>SCSI Multimedia 3</i> (<i>MMC-3</i>) specification for a description of the values that this member can take. <b>DataTypeSupported</b>[0] holds the most significant byte of value that indicates the data types. <b>DataTypeSupported</b>[1] holds the least significant byte of that value. 


## -remarks
This structure holds data for the feature named "CD Track at Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a CD track.


## -see-also
<dl>
<dt>
<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>
</dt>
<dt>
<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CD_TRACK_AT_ONCE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

