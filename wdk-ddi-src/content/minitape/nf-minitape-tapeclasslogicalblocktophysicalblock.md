---
UID: NF:minitape.TapeClassLogicalBlockToPhysicalBlock
title: TapeClassLogicalBlockToPhysicalBlock function (minitape.h)
description: The TapeClassLogicalBlockToPhysicalBlock routine translates a pseudological block address to a physical block address. This routine is for SCSI-1 devices.
old-location: storage\tapeclasslogicalblocktophysicalblock.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TapeClassLogicalBlockToPhysicalBlock function"]
ms.keywords: TapeClassLogicalBlockToPhysicalBlock, TapeClassLogicalBlockToPhysicalBlock routine [Storage Devices], minitape/TapeClassLogicalBlockToPhysicalBlock, storage.tapeclasslogicalblocktophysicalblock, tapeclas_6d45358d-68a6-4f00-991e-714a489fd78d.xml
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
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
req.lib: Tape.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - TapeClassLogicalBlockToPhysicalBlock
 - minitape/TapeClassLogicalBlockToPhysicalBlock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Tape.lib
 - Tape.dll
api_name:
 - TapeClassLogicalBlockToPhysicalBlock
---

# TapeClassLogicalBlockToPhysicalBlock function


## -description

The <b>TapeClassLogicalBlockToPhysicalBlock</b> routine translates a pseudological block address to a physical block address. This routine is for SCSI-1 devices.

## -parameters

### -param DensityCode [in]


Specifies the tape media density code. This routine supports tapes with the following density codes: QIC_24, QIC_120, QIC_150, QIC_525, QIC_1000, QIC_2GB, QIC_1350, and QIC_2100.

### -param LogicalBlockAddress [in]


Specifies a pseudological block address.

### -param BlockLength [in]


Specifies the logical block size, in bytes.

### -param FromBOT [in]


<b>TRUE</b> indicates that the physical block calculation should start at the beginning of the tape and account for the physical device header. <b>FALSE</b> indicates that the tape has two partitions, that the block address is on the directory partition, and therefore no physical device header needs to be factored into the calculation.

## -returns

<b>TapeClassLogicalBlockToPhysicalBlock</b> returns a structure containing the physical block address:
      

typedef struct _TAPE_PHYS_POSITION {

ULONG SeekBlockAddress;

ULONG SpaceBlockCount;

} TAPE_PHYS_POSITION, PTAPE_PHYS_POSITION;

## -remarks

A tape miniclass driver calls <b>TapeClassLogicalBlockToPhysicalBlock</b> to translate a logical block address from an application to a physical block address for a tape device. <b>TapeClassLogicalBlockToPhysicalBlock</b> is not necessary for SCSI-2 or later drivers because devices that comply with SCSI-2 or later standards support logical block addressing.

To position a tape to the physical block address returned by this routine, a tape miniclass driver issues two SCSI commands: a LOCATE command to position the tape to the <b>SeekBlockAddress</b>, and then a SPACE command to advance the tape <b>SpaceBlockCount</b>. The <b>SpaceBlockCount</b> value is necessary if the pseudological blocks on the tape are smaller than the physical blocks; in that case, the logical block boundary might not align with a physical block boundary.

If a tape miniclass driver calls this routine with an unsupported tape density code, <b>TapeClassLogicalBlockToPhysicalBlock</b> does not perform any translation. It returns the logical block address in <b>SeekBlockAddress</b> and returns zero in <b>SpaceBlockCount</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/minitape/nf-minitape-tapeclassphysicalblocktologicalblock">TapeClassPhysicalBlockToLogicalBlock</a>
