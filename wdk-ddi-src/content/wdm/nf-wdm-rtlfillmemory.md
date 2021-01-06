---
UID: NF:wdm.RtlFillMemory
title: RtlFillMemory macro (wdm.h)
description: The RtlFillMemory routine fills a block of memory with the specified fill value.
old-location: kernel\rtlfillmemory.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlFillMemory macro"]
ms.keywords: RtlFillMemory, RtlFillMemory routine [Kernel-Mode Driver Architecture], k109_db7a2a9f-c7b5-40c3-9755-e386bbaf5353.xml, kernel.rtlfillmemory, wdm/RtlFillMemory
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFillMemory
 - wdm/RtlFillMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-rtlsupport-l1-1-0.dll
api_name:
 - RtlFillMemory
---

# RtlFillMemory macro


## -description

The <b>RtlFillMemory</b> routine fills a block of memory with the specified fill value.

## -parameters

### -param Destination 

[out]
A pointer to the block of memory to be filled.

### -param Length 

[in]
The number of bytes in the block of memory to be filled.

### -param Fill 

[in]
The value to fill the destination memory block with. This value is copied to every byte in the memory block that is defined by <i>Destination</i> and <i>Length</i>.

## -syntax

```
void RtlFillMemory(
   void*  Destination,
   size_t Length
   int    Fill
);
```

## -remarks

Callers of <b>RtlFillMemory</b> can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>
