---
UID: NF:wdm.RtlMoveMemory
title: RtlMoveMemory macro (wdm.h)
description: The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["RtlMoveMemory macro"]
ms.keywords: RtlMoveMemory, RtlMoveMemory routine [Kernel-Mode Driver Architecture], k109_5731ba5b-a7a5-4883-87cf-543768a29a93.xml, kernel.rtlmovememory, wdm/RtlMoveMemory
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlMoveMemory
 - wdm/RtlMoveMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlMoveMemory
---

## -description

The **RtlMoveMemory** routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.

## -parameters

### -param Destination [out]

A pointer to the destination memory block to copy the bytes to.

### -param Source [in]

A pointer to the source memory block to copy the bytes from.

### -param Length [in]

The number of bytes to copy from the source to the destination.

## -syntax

```cpp
void RtlMoveMemory(
   void*       Destination,
   const void* Source,
   size_t      Length
);
```

## -remarks

The source memory block, which is defined by *Source* and *Length*, can overlap the destination memory block, which is defined by *Destination* and *Length*.

The [RtlCopyMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory) routine runs faster than **RtlMoveMemory**, but **RtlCopyMemory** requires that the source and destination memory blocks do not overlap.

Callers of **RtlMoveMemory** can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[RtlCopyMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory)
