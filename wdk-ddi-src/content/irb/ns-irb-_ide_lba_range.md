---
UID: NS:irb._IDE_LBA_RANGE
title: "_IDE_LBA_RANGE"
author: windows-driver-content
description: The IDE_LBA_RANGE structure is used by the port driver to provide the miniport driver with a range of logical blocks.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_lba_range.htm
old-project: storage
ms.assetid: 2d823d9c-7328-44e2-9ba2-22967471ef68
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PIDE_LBA_RANGE, ,, A, B, D, E, G, I, IDE_LBA_RANGE, IDE_LBA_RANGE structure [Storage Devices], L, N, P, PIDE_LBA_RANGE, PIDE_LBA_RANGE structure pointer [Storage Devices], R, _, _IDE_LBA_RANGE, irb/IDE_LBA_RANGE, irb/PIDE_LBA_RANGE, storage.ide_lba_range, structs-ATA_0abd91d5-18f0-49c9-b5de-ac442718da3f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	IDE_LBA_RANGE
product: Windows
targetos: Windows
req.typenames: IDE_LBA_RANGE, *PIDE_LBA_RANGE
---

# _IDE_LBA_RANGE structure


## -description


The IDE_LBA_RANGE structure is used by the port driver to provide the miniport driver with a range of logical blocks.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_LBA_RANGE {
  ULONGLONG StartSector  :48;
  ULONGLONG SectorCount  :16;
} IDE_LBA_RANGE, *PIDE_LBA_RANGE;
````


## -struct-fields




### -field StartSector

Contains the starting sector of the LBA range.


### -field SectorCount

Contains the sector count of the LBA range.

