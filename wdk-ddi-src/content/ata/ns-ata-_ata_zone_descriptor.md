---
UID: NS:ata._ATA_ZONE_DESCRIPTOR
title: "_ATA_ZONE_DESCRIPTOR"
author: windows-driver-content
description: This structure is for internal use only and should not be called from your code.
old-location: storage\ata_zone_descriptor.htm
old-project: storage
ms.assetid: 2e027ac5-7b5d-43cc-8d37-c0a3e77e68c9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ATA_ZONE_DESCRIPTOR structure [Storage Devices], PATA_ZONE_DESCRIPTOR structure pointer [Storage Devices], ata/ATA_ZONE_DESCRIPTOR, storage.ata_zone_descriptor, ATA_ZONE_DESCRIPTOR, PATA_ZONE_DESCRIPTOR, _ATA_ZONE_DESCRIPTOR, *PATA_ZONE_DESCRIPTOR, ata/PATA_ZONE_DESCRIPTOR
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
-	Ata.h
apiname:
-	ATA_ZONE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PATA_ZONE_DESCRIPTOR, ATA_ZONE_DESCRIPTOR"
---

# _ATA_ZONE_DESCRIPTOR structure


## -description


This structure is for internal use only and should not be called from your code.


## -syntax


````
typedef struct _ATA_ZONE_DESCRIPTOR {
  UCHAR     ZoneType  : 4;
  UCHAR     Reserved0  : 4;
  UCHAR     Reset  : 1;
  UCHAR     NonSeq : 1;
  UCHAR     Reserved1  : 2;
  UCHAR     ZoneCondition  : 4;
  UCHAR     Reserved2[6];
  ULONGLONG ZoneLength  : 48;
  ULONGLONG Reserved3  : 16;
  ULONGLONG ZoneStartLBA  : 48;
  ULONGLONG Reserved4  : 16;
  ULONGLONG WritePointerLBA  : 48;
  ULONGLONG Reserved5  : 16;
  UCHAR     Reserved6[32];
} ATA_ZONE_DESCRIPTOR, *PATA_ZONE_DESCRIPTOR;
````


## -struct-fields




### -field ZoneType

 


### -field Reserved0

 


### -field Reset

 


### -field NonSeq

 


### -field Reserved1

 


### -field ZoneCondition

 


### -field Reserved2

N/A


### -field ZoneLength

 


### -field Reserved3

 


### -field ZoneStartLBA

 


### -field Reserved4

 


### -field WritePointerLBA

 


### -field Reserved5

 


### -field Reserved6

N/A


#### - NonSeq : 1

N/A


#### - Reserved0  : 4

N/A


#### - Reserved1  : 2

N/A


#### - Reserved3  : 16

N/A

N/A


#### - Reserved4  : 16

N/A


#### - Reserved5  : 16

N/A


#### - Reset  : 1

N/A


#### - WritePointerLBA  : 48

N/A


#### - ZoneCondition  : 4

N/A


#### - ZoneLength  : 48

N/A


#### - ZoneStartLBA  : 48

N/A


#### - ZoneType  : 4

N/A

