---
UID: NS:ata._REPORT_ZONES_EXT_DATA
title: "_REPORT_ZONES_EXT_DATA"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\report_zones_ext_data.htm
old-project: storage
ms.assetid: 0c6b4b7c-548d-42c0-af9b-cf0d65bf2e45
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PREPORT_ZONES_EXT_DATA structure pointer [Storage Devices], ata/REPORT_ZONES_EXT_DATA, PREPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA, ata/PREPORT_ZONES_EXT_DATA, _REPORT_ZONES_EXT_DATA, REPORT_ZONES_EXT_DATA, REPORT_ZONES_EXT_DATA structure [Storage Devices], storage.report_zones_ext_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ata.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ata.h
apiname:
-	REPORT_ZONES_EXT_DATA
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---

# _REPORT_ZONES_EXT_DATA structure


## -description



<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax


````
typedef struct _REPORT_ZONES_EXT_DATA {
  ULONG     ZoneListLength;
  UCHAR     SAME  :4;
  UCHAR     Reserved0  :4;
  UCHAR     Reserved1[3];
  ULONGLONG MaxLBA  :48;
  ULONGLONG Reserved2  :16;
  UCHAR     Reserved3[48];
} REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA;
````


## -struct-fields




### -field ZoneListLength

N/A


### -field SAME

N/A


### -field Reserved0

Reserved for future use.


### -field Reserved1

Reserved for future use.


### -field MaxLBA

N/A


### -field Reserved2

Reserved for future use.


### -field Reserved3

Reserved for future use.

