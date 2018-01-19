---
UID: NS:storport._REPORT_ZONES_DATA
title: _REPORT_ZONES_DATA
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\report_zones_data.htm
old-project: storage
ms.assetid: 67785cb0-388c-4348-b32a-99bcd02b7c04
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _REPORT_ZONES_DATA, *PREPORT_ZONES_DATA, REPORT_ZONES_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REPORT_ZONES_DATA
req.alt-loc: scsi.h
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
req.typenames: *PREPORT_ZONES_DATA, REPORT_ZONES_DATA
req.product: Windows 10 or later.
---

# _REPORT_ZONES_DATA structure



## -description

<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>




## -syntax

````
typedef struct _REPORT_ZONES_DATA {
  UCHAR            ZoneListLength[4];
  UCHAR            Same  :4;
  UCHAR            Reserved1  :4;
  UCHAR            Reserved2[4];
  UCHAR            MaxLBA[8];
  UCHAR            Reserved3[48];
#ifndef (__midl)
  ZONE_DESCRIPTIOR ZoneDescriptors[ANYSIZE_ARRAY];
#endif 
} REPORT_ZONES_DATA, *PREPORT_ZONES_DATA;
````


## -struct-fields

### -field ZoneListLength

N/A


### -field Same

N/A


### -field Reserved1

N/A


### -field Reserved2

N/A


### -field MaxLBA

N/A


### -field Reserved3

N/A


### -field ZoneDescriptors

N/A


## -remarks
