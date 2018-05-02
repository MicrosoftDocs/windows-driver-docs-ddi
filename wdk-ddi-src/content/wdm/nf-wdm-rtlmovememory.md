---
UID: NF:wdm.RtlMoveMemory
title: RtlMoveMemory macro
author: windows-driver-content
description: The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.
old-location: kernel\rtlmovememory.htm
old-project: kernel
ms.assetid: f6727247-e704-42d7-b4f1-ce7d20e317bb
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlMoveMemory, RtlMoveMemory routine [Kernel-Mode Driver Architecture], k109_5731ba5b-a7a5-4883-87cf-543768a29a93.xml, kernel.rtlmovememory, wdm/RtlMoveMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlMoveMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlMoveMemory macro


## -description


The <b>RtlMoveMemory</b> routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.


## -parameters




### -param Destination [out]

A pointer to the destination memory block to copy the bytes to.


### -param Source [in]

A pointer to the source memory block to copy the bytes from.


### -param Length [in]

The number of bytes to copy from the source to the destination.


## -remarks



The source memory block, which is defined by <i>Source</i> and <i>Length</i>, can overlap the destination memory block, which is defined by <i>Destination</i> and <i>Length</i>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a> routine runs faster than <b>RtlMoveMemory</b>, but <b>RtlCopyMemory</b> requires that the source and destination memory blocks do not overlap.

Callers of <b>RtlMoveMemory</b> can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561808">RtlCopyMemory</a>
 

 

