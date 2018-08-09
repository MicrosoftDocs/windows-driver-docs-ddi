---
UID: NF:wdm.RtlCopyMemoryNonTemporal
title: RtlCopyMemoryNonTemporal function
author: windows-driver-content
description: This function copies from one buffer to another using non-temporal moves that do not pollute the cache. The buffers shouldn’t overlap.
ms.assetid: 08dadbdf-95e4-4998-bdc3-dfc2528f028e
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: RtlCopyMemoryNonTemporal
req.header: wdm.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2003 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.irql: Any level (see Remarks section)
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtDll.dll
-	NtosKrnl.exe
api_name: 
-	RtlCopyMemoryNonTemporal
product:
-	Windows
targetos: Windows


---

# RtlCopyMemoryNonTemporal function


## -description

This function copies the contents from one buffer to another using non-temporal moves that do not pollute the cache. Note that the buffers shouldn’t overlap.

## -parameters

### -param Length
The number of bytes to copy from the source to the destination.

### -param Source
A pointer to the source memory block to copy the bytes from.

### -param Destination
A pointer to the destination memory block to copy the bytes to.

## -returns
None.

## -remarks

**RtlCopyMemoryNonTemporal** only performs a non-temporal copy for x64-based systems, and only when the **Length** parameter is 8 bytes or greater. Otherwise, this function is equivalent to [RtlCopyMemory](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcopymemory).

Callers of RtlCopyMemoryNonTemporal can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.


## -see-also

[RtlCopyMemory](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcopymemory)