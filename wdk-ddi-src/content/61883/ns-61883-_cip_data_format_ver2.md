---
UID: NS:61883._CIP_DATA_FORMAT_VER2
title: "_CIP_DATA_FORMAT_VER2" (61883.h)
description: This structure is a CIP data format which is used by CMP_CONNECT_VER2.
old-location: ieee\cip_data_format_ver2.htm
tech.root: IEEE
ms.assetid: C78543F5-82CC-43CF-8769-1E721C17FF9C
ms.date: 02/15/2018
ms.keywords: "*PCIP_DATA_FORMAT, *PCIP_DATA_FORMAT_VER2, 61883/CIP_DATA_FORMAT_VER2, 61883/PCIP_DATA_FORMAT_VER2, CIP_DATA_FORMAT, CIP_DATA_FORMAT_VER2, CIP_DATA_FORMAT_VER2 structure [Buses], IEEE.cip_data_format_ver2, PCIP_DATA_FORMAT_VER2, PCIP_DATA_FORMAT_VER2 structure pointer [Buses], _CIP_DATA_FORMAT_VER2"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CIP_DATA_FORMAT_VER2
product:
- Windows
targetos: Windows
req.typenames: CIP_DATA_FORMAT_VER2, *PCIP_DATA_FORMAT_VER2
---

# _CIP_DATA_FORMAT_VER2 structure


## -description


This structure is a CIP data format which is used by <a href="https://msdn.microsoft.com/2A2C1478-0512-4F84-90B9-B9C62B5D44DA">CMP_CONNECT_VER2</a>.


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

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537045">CIP_FRAME</a> structure that contains information about a frame and a data buffer to be sent or filled.


#### - hConnect

A handle to a connection.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

