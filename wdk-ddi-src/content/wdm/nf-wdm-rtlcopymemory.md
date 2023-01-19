---
UID: NF:wdm.RtlCopyMemory
title: RtlCopyMemory macro (wdm.h)
description: Learn how the RtlCopyMemory routine copies the contents of a source memory block to a destination memory block.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["RtlCopyMemory macro"]
ms.keywords: RtlCopyBytes, RtlCopyMemory, RtlCopyMemory routine [Kernel-Mode Driver Architecture], k109_f4bb1fef-aae6-4086-b95a-ae4dc220c04b.xml, kernel.rtlcopymemory, wdm/RtlCopyMemory
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCopyMemory
 - wdm/RtlCopyMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-Rtlsupport-l1-1-0.dll
api_name:
 - RtlCopyMemory
---

## -description

The **RtlCopyMemory** routine copies the contents of a source memory block to a destination memory block.

## -parameters

### -param Destination [out]

A pointer to the destination memory block to copy the bytes to.

### -param Source [in]

A pointer to the source memory block to copy the bytes from.

### -param Length [in]

The number of bytes to copy from the source to the destination.

## -syntax

```cpp
void RtlCopyMemory(
   void*       Destination,
   const void* Source,
   size_t      Length
);
```

## -remarks

**RtlCopyMemory** runs faster than **RtlMoveMemory**. However, **RtlCopyMemory** requires that the source memory block, which is defined by *Source* and *Length*, cannot overlap the destination memory block, which is defined by *Destination* and *Length*. In contrast, **RtlMoveMemory** correctly handles the case in which the source and destination memory blocks overlap.

New drivers should use the **RtlCopyMemory** routine instead of **RtlCopyBytes**.

Callers of **RtlCopyMemory** can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[RtlMoveMemory](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlmovememory)
