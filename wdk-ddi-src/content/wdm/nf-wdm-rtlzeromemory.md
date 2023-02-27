---
UID: NF:wdm.RtlZeroMemory
title: RtlZeroMemory macro (wdm.h)
description: The RtlZeroMemory macro (wdm.h) fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["RtlZeroMemory macro"]
ms.keywords: RtlZeroMemory, RtlZeroMemory routine [Kernel-Mode Driver Architecture], k109_63d9f0fb-d698-4707-9018-de2fa851a94b.xml, kernel.rtlzeromemory, wdm/RtlZeroMemory
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Smclib.h, Minitape.h, Scsi.h, Storport.h
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
 - RtlZeroMemory
 - wdm/RtlZeroMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlZeroMemory
---

## -description

The **RtlZeroMemory** routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled.

## -parameters

### -param Destination [out]

A pointer to the memory block to be filled with zeros.

### -param Length [in]

The number of bytes to fill with zeros.

## -syntax

```cpp
void RtlZeroMemory(
   void*  Destination,
   size_t Length
);
```

## -remarks

To zero out a memory buffer to erase security-sensitive data, use [RtlSecureZeroMemory](./nf-wdm-rtlsecurezeromemory.md) instead.

Callers of **RtlZeroMemory** can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[RtlFillMemory](./nf-wdm-rtlfillmemory.md)

[RtlSecureZeroMemory](./nf-wdm-rtlsecurezeromemory.md)