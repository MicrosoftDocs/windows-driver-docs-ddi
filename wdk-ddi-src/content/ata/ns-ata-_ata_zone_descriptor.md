---
UID: NS:ata._ATA_ZONE_DESCRIPTOR
title: _ATA_ZONE_DESCRIPTOR (ata.h)
description: This structure is for internal use only and should not be called from your code.
old-location: storage\ata_zone_descriptor.htm
tech.root: storage
ms.assetid: 2e027ac5-7b5d-43cc-8d37-c0a3e77e68c9
ms.date: 03/29/2018
keywords: ["ATA_ZONE_DESCRIPTOR structure"]
ms.keywords: "*PATA_ZONE_DESCRIPTOR, ATA_ZONE_DESCRIPTOR, ATA_ZONE_DESCRIPTOR structure [Storage Devices], PATA_ZONE_DESCRIPTOR, PATA_ZONE_DESCRIPTOR structure pointer [Storage Devices], _ATA_ZONE_DESCRIPTOR, ata/ATA_ZONE_DESCRIPTOR, ata/PATA_ZONE_DESCRIPTOR, storage.ata_zone_descriptor"
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
targetos: Windows
req.typenames: ATA_ZONE_DESCRIPTOR, *PATA_ZONE_DESCRIPTOR
f1_keywords:
 - _ATA_ZONE_DESCRIPTOR
 - ata/_ATA_ZONE_DESCRIPTOR
 - PATA_ZONE_DESCRIPTOR
 - ata/PATA_ZONE_DESCRIPTOR
 - ATA_ZONE_DESCRIPTOR
 - ata/ATA_ZONE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ata.h
api_name:
 - ATA_ZONE_DESCRIPTOR
---

# _ATA_ZONE_DESCRIPTOR structure


## -description

This structure is for internal use only and should not be called from your code.

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

