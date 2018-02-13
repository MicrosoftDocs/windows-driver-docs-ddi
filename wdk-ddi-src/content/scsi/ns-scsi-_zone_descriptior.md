---
UID: NS:scsi._ZONE_DESCRIPTIOR
title: "_ZONE_DESCRIPTIOR"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\zone_descriptior.htm
old-project: storage
ms.assetid: 8326f683-3952-486e-b322-80ce96759366
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ZONE_DESCRIPTIOR, PZONE_DESCRIPTIOR, storage.zone_descriptior, _ZONE_DESCRIPTIOR, scsi/ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR, scsi/PZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR structure [Storage Devices], PZONE_DESCRIPTIOR structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
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
-	scsi.h
apiname:
-	ZONE_DESCRIPTIOR
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# _ZONE_DESCRIPTIOR structure


## -description



<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax


````
typedef struct _ZONE_DESCRIPTIOR {
  UCHAR      ZoneType  :4;
  UCHAR      Reserved1  :4;
  UCHAR  : 1 Reset  :1;
  UCHAR      Non_Seq  :1;
  UCHAR      Reserved2  :2;
  UCHAR      ZoneCondition  :4;
  UCHAR      Reserved3[6];
  UCHAR      ZoneLength[8];
  UCHAR      ZoneStartLBA[8];
  UCHAR      WritePointerLBA[8];
  UCHAR      Reserved4[32];
} ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR;
````


## -struct-fields




### -field ZoneType

N/A


### -field Reserved1

N/A


### -field Reset

N/A


### -field Non_Seq

N/A


### -field Reserved2

N/A


### -field ZoneCondition

N/A


### -field Reserved3

N/A


### -field ZoneLength

N/A


### -field ZoneStartLBA

N/A


### -field WritePointerLBA

N/A


### -field Reserved4

N/A

