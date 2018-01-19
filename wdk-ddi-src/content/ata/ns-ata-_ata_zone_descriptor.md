---
UID: NS:ata._ATA_ZONE_DESCRIPTOR
title: _ATA_ZONE_DESCRIPTOR
author: windows-driver-content
description: This structure is for internal use only and should not be called from your code.
old-location: storage\ata_zone_descriptor.htm
old-project: storage
ms.assetid: 2e027ac5-7b5d-43cc-8d37-c0a3e77e68c9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _ATA_ZONE_DESCRIPTOR, *PATA_ZONE_DESCRIPTOR, ATA_ZONE_DESCRIPTOR
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
req.alt-api: ATA_ZONE_DESCRIPTOR
req.alt-loc: Ata.h
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
req.typenames: *PATA_ZONE_DESCRIPTOR, ATA_ZONE_DESCRIPTOR
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

### -field ZoneType  : 4

N/A


### -field Reserved0  : 4

N/A


### -field Reset  : 1

N/A


### -field NonSeq : 1

N/A


### -field Reserved1  : 2

N/A


### -field ZoneCondition  : 4

N/A


### -field Reserved2

N/A


### -field ZoneLength  : 48

N/A


### -field Reserved3  : 16

N/A

N/A


### -field ZoneStartLBA  : 48

N/A


### -field Reserved4  : 16

N/A


### -field WritePointerLBA  : 48

N/A


### -field Reserved5  : 16

N/A


### -field Reserved6

N/A


## -remarks
