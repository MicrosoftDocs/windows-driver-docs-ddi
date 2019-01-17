---
UID: NS:irb._IDE_LBA_RANGE
title: "_IDE_LBA_RANGE"
description: The IDE_LBA_RANGE structure is used by the port driver to provide the miniport driver with a range of logical blocks.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_lba_range.htm
tech.root: storage
ms.assetid: 2d823d9c-7328-44e2-9ba2-22967471ef68
ms.date: 03/29/2018
ms.keywords: "*PIDE_LBA_RANGE, IDE_LBA_RANGE, IDE_LBA_RANGE structure [Storage Devices], PIDE_LBA_RANGE, PIDE_LBA_RANGE structure pointer [Storage Devices], _IDE_LBA_RANGE, irb/IDE_LBA_RANGE, irb/PIDE_LBA_RANGE, storage.ide_lba_range, structs-ATA_0abd91d5-18f0-49c9-b5de-ac442718da3f.xml"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_LBA_RANGE
product:
- Windows
targetos: Windows
req.typenames: IDE_LBA_RANGE, *PIDE_LBA_RANGE
---

# _IDE_LBA_RANGE structure


## -description


The IDE_LBA_RANGE structure is used by the port driver to provide the miniport driver with a range of logical blocks.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field StartSector

Contains the starting sector of the LBA range.


### -field SectorCount

Contains the sector count of the LBA range.

