---
UID: NS:61883._CIP_DATA_FORMAT_VER2
title: _CIP_DATA_FORMAT_VER2 (61883.h)
description: This structure is a CIP data format which is used by CMP_CONNECT_VER2.
old-location: ieee\cip_data_format_ver2.htm
tech.root: IEEE
ms.assetid: C78543F5-82CC-43CF-8769-1E721C17FF9C
ms.date: 02/15/2018
ms.keywords: "*PCIP_DATA_FORMAT, *PCIP_DATA_FORMAT_VER2, 61883/CIP_DATA_FORMAT_VER2, 61883/PCIP_DATA_FORMAT_VER2, CIP_DATA_FORMAT, CIP_DATA_FORMAT_VER2, CIP_DATA_FORMAT_VER2 structure [Buses], IEEE.cip_data_format_ver2, PCIP_DATA_FORMAT_VER2, PCIP_DATA_FORMAT_VER2 structure pointer [Buses], _CIP_DATA_FORMAT_VER2"
ms.topic: struct
f1_keywords:
 - "61883/CIP_DATA_FORMAT_VER2"
req.header: 61883.h
req.include-header: 
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
- 61883.h
api_name:
- CIP_DATA_FORMAT_VER2
product:
- Windows
targetos: Windows
req.typenames: CIP_DATA_FORMAT_VER2, *PCIP_DATA_FORMAT_VER2
---

# _CIP_DATA_FORMAT_VER2 structure


## -description


This structure is a CIP data format which is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/61883/ns-61883-_cmp_connect_ver2">CMP_CONNECT_VER2</a>.


## -struct-fields




### -field FMT

 


### -field FDF_hi

 


### -field FDF_mid

 


### -field FDF_lo

 


### -field bHeader

 


### -field Padding

 


### -field BlockSize

 


### -field Fraction

 


### -field BlockPeriod

 




#### - Frame

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/61883/ns-61883-_cip_frame">CIP_FRAME</a> structure that contains information about a frame and a data buffer to be sent or filled.


#### - hConnect

A handle to a connection.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

