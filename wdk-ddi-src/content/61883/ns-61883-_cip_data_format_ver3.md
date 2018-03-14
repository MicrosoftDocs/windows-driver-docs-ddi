---
UID: NS:61883._CIP_DATA_FORMAT_VER3
title: "_CIP_DATA_FORMAT_VER3"
author: windows-driver-content
description: This structure is used by CipDataFormat.
old-location: ieee\cip_data_format_ver3.htm
old-project: IEEE
ms.assetid: A7EDC949-A2C6-43E9-9CA0-886FEE5282F5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCIP_DATA_FORMAT, *PCIP_DATA_FORMAT_VER3, 61883/CIP_DATA_FORMAT_VER3, 61883/PCIP_DATA_FORMAT_VER3, CIP_DATA_FORMAT, CIP_DATA_FORMAT_VER3, CIP_DATA_FORMAT_VER3 structure [Buses], IEEE.cip_data_format_ver3, PCIP_DATA_FORMAT_VER3, PCIP_DATA_FORMAT_VER3 structure pointer [Buses], _CIP_DATA_FORMAT_VER3"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	CIP_DATA_FORMAT_VER3
product: Windows
targetos: Windows
req.typenames: CIP_DATA_FORMAT_VER3, *PCIP_DATA_FORMAT_VER3
---

# _CIP_DATA_FORMAT_VER3 structure


## -description


This structure is used by  	<b>CipDataFormat</b>.


## -syntax


````
typedef struct _CIP_DATA_FORMAT_VER3 {
  UCHAR   FMT;
  UCHAR   FDF_hi;
  UCHAR   FDF_mid;
  UCHAR   FDF_lo;
  BOOLEAN bHeader;
  UCHAR   Padding;
  UCHAR   BlockSize;
  UCHAR   Fraction;
  ULONG   BlockPeriod;
  ULONG   BlockPeriodRemainder;
  ULONG   BlocksPerPacket;
} CIP_DATA_FORMAT_VER3, *PCIP_DATA_FORMAT_VER3;
````


## -struct-fields




### -field FMT

This member is either known, or discovered by an AV/C command.


### -field FDF_hi

This member is either known, or discovered by an AV/C command.


### -field FDF_mid

This member is either known, or discovered by an AV/C command.


### -field FDF_lo

This member is either known, or discovered by an AV/C command.


### -field bHeader

This member is SPH as defined by IEC-61883.


### -field Padding

This member is QPC as defined by IEC-61883.


### -field BlockSize

This member is DBS as defined by IEC-61883.


### -field Fraction

This member is FN as defined by IEC-61883.


### -field BlockPeriod

This member is the number of 1394 ticks to send a data block.


### -field BlockPeriodRemainder

This member is the remainder of 1394 ticks to send a data block.


### -field BlocksPerPacket

This member is the number of blocks per packet; used for blocking mode only


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 


