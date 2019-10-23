---
UID: NS:ntddmmc._FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE
title: _FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE (ntddmmc.h)
description: The FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE structure contains information about the Incremental Streaming Writable feature.
old-location: storage\feature_data_incremental_streaming_writable.htm
tech.root: storage
ms.assetid: 5e3918a4-8cc6-45b9-acb1-3a2b2088d4b9
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE structure [Storage Devices], PFEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, PFEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE structure pointer [Storage Devices], _FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, ntddmmc/FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, ntddmmc/PFEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, storage.feature_data_incremental_streaming_writable, structs-CD-ROM_ad0cd0d4-fa5d-4ad4-82d9-7945eaa2a2cd.xml"
ms.topic: struct
f1_keywords:
 - "ntddmmc/FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE"
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
- FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE, *PFEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE
---

# _FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE structure


## -description


The FEATURE_DATA_INCREMENTAL_STREAMING_WRITABLE structure contains information about the Incremental Streaming Writable feature. 


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field DataTypeSupported

Indicates the supported data type. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for an explanation of the values that this member can take. <b>DataTypeSupported</b>[0] must hold the most significant byte of the number of the data type. <b>DataTypeSupported</b>[1] must hold the least significant byte of the number.


### -field BufferUnderrunFree

Indicates, when set to one, that the logical unit is capable of zero-loss linking.


### -field AddressModeReservation


### -field TrackRessourceInformation


### -field Reserved01


### -field NumberOfLinkSizes

Specifies the number of link sizes available for the current media. See the <i>MMC-3</i> specification for an explanation of the values that this member can take. 


### -field LinkSize

Contains an array that indicates the number of logical blocks per link. 


## -remarks



This structure holds data for the feature named "Incremental Streaming Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can write data to a contiguous region, and can append data to a limited number of locations on the media. On CD media, this is known as "packet recording" and on a DVD media it is known as "incremental recording".




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

