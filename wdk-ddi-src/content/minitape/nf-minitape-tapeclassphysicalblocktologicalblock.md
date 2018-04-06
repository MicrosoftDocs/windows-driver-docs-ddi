---
UID: NF:minitape.TapeClassPhysicalBlockToLogicalBlock
title: TapeClassPhysicalBlockToLogicalBlock function
author: windows-driver-content
description: The TapeClassPhysicalBlockToLogicalBlock routine translates a physical block address to a pseudological block address. This routine is for SCSI-1 devices.
old-location: storage\tapeclassphysicalblocktologicalblock.htm
old-project: storage
ms.assetid: fc95f5c8-2892-479d-ac25-32c07e9c7aab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: TapeClassPhysicalBlockToLogicalBlock, TapeClassPhysicalBlockToLogicalBlock routine [Storage Devices], minitape/TapeClassPhysicalBlockToLogicalBlock, storage.tapeclassphysicalblocktologicalblock, tapeclas_94d20234-ee4d-4096-b856-f5196b606e2d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Tape.lib
-	Tape.dll
api_name:
-	TapeClassPhysicalBlockToLogicalBlock
product:
- Windows
targetos: Windows
req.typenames: TAPE_STATUS, *PTAPE_STATUS
---

# TapeClassPhysicalBlockToLogicalBlock function


## -description


The <b>TapeClassPhysicalBlockToLogicalBlock</b> routine translates a physical block address to a pseudological block address. This routine is for SCSI-1 devices.


## -parameters




### -param DensityCode [in]

Specifies the tape media density code. This routine supports tapes with the following density codes: QIC_24, QIC_120, QIC_150, QIC_525, QIC_1000, QIC_2GB, QIC_1350, and QIC_2100.


### -param PhysicalBlockAddress [in]

Specifies the physical block address obtained by a SCSI READ POSITION command.


### -param BlockLength [in]

Specifies the logical block size, in bytes.


### -param FromBOT [in]

<b>TRUE</b> indicates that the logical block calculation should start at the beginning of the tape and account for the physical device header. <b>FALSE</b> indicates that the tape has two partitions, that the block address is on the directory partition, and therefore no physical device header needs to be factored into the calculation.


## -returns



<b>TapeClassPhysicalBlockToLogicalBlock</b> returns the logical block address.




## -remarks



A tape miniclass driver calls <b>TapeClassPhysicalBlockToLogicalBlock</b> to translate a physical block address from a tape device to a logical block address for an application. <b>TapeClassPhysicalBlockToLogicalBlock</b> is not necessary for SCSI-2 or later drivers because devices that comply with SCSI-2 or later standards support logical block addressing.

If a tape miniclass driver calls this routine with an unsupported tape density code, <b>TapeClassPhysicalBlockToLogicalBlock </b>returns the physical block address in the return value, without performing any translation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567623">TapeClassLogicalBlockToPhysicalBlock</a>
 

 

