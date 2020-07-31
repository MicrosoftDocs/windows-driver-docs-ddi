---
UID: NS:irb._IDE_ACCESS_RANGE
title: _IDE_ACCESS_RANGE (irb.h)
description: The IDE_ACCESS_RANGE structure contains the address ranges allocated for an IDE controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_access_range.htm
tech.root: storage
ms.assetid: e81441a2-0659-4d32-97f4-415abef6c87a
ms.date: 03/29/2018
keywords: ["_IDE_ACCESS_RANGE structure"]
ms.keywords: "*PIDE_ACCESS_RANGE, IDE_ACCESS_RANGE, IDE_ACCESS_RANGE structure [Storage Devices], PIDE_ACCESS_RANGE, PIDE_ACCESS_RANGE structure pointer [Storage Devices], _IDE_ACCESS_RANGE, irb/IDE_ACCESS_RANGE, irb/PIDE_ACCESS_RANGE, storage.ide_access_range, structs-ATA_6c50e733-2896-4052-a867-ae2c9d119ff2.xml"
f1_keywords:
 - "irb/IDE_ACCESS_RANGE"
 - "IDE_ACCESS_RANGE"
req.header: irb.h
req.include-header: Irb.h
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
- irb.h
api_name:
- IDE_ACCESS_RANGE
targetos: Windows
req.typenames: IDE_ACCESS_RANGE, *PIDE_ACCESS_RANGE
---

# _IDE_ACCESS_RANGE structure


## -description


The IDE_ACCESS_RANGE structure contains the address ranges allocated for an IDE controller.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field RangeStart

Contains the logical starting address of the address range.


### -field PhysicalRangeStart

Contains the physical starting address of the address range.


### -field RangeLength

Contains the size, in bytes, of the range.


### -field InMemory

Flag that indicates if this is a memory mapped resource. If cleared, this is an I/O port resource.


### -field Bar

The number of the PCI Base Address Range that this resource was found in.

