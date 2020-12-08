---
UID: NF:ntifs.RtlCompareMemoryUlong
title: RtlCompareMemoryUlong function (ntifs.h)
description: The RtlCompareMemoryUlong routine returns how many bytes in a block of memory match a specified pattern.
old-location: ifsk\rtlcomparememoryulong.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlCompareMemoryUlong function"]
ms.keywords: RtlCompareMemoryUlong, RtlCompareMemoryUlong routine [Installable File System Drivers], ifsk.rtlcomparememoryulong, ntifs/RtlCompareMemoryUlong, rtlref_a220e168-945b-46d1-9aa7-7750bdfc39bd.xml
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCompareMemoryUlong
 - ntifs/RtlCompareMemoryUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlCompareMemoryUlong
---

# RtlCompareMemoryUlong function


## -description

The <b>RtlCompareMemoryUlong</b> routine returns how many bytes in a block of memory match a specified pattern.

## -parameters

### -param Source 

[in]
Pointer to a block of memory. Must be aligned on a ULONG boundary.

### -param Length 

[in]
Number of bytes over which the comparison should be done. Must be a multiple of <b>sizeof(</b>ULONG<b>)</b>.

### -param Pattern 

[in]
Pattern to be compared byte by byte, repeatedly, through the specified memory range.

## -returns

<b>RtlCompareMemoryUlong</b> returns the number of bytes that were compared and found to be equal. If all bytes compare as equal, the input <i>Length</i> is returned. <b>RtlCompareMemoryUlong</b> returns zero if <i>Source</i> is not ULONG-aligned or if <i>Length</i> is not a multiple of <b>sizeof(</b>ULONG<b>)</b>.

## -remarks

If the block of memory at <i>Source</i> is nonpaged, the caller can be running at any IRQL. Otherwise, callers of <b>RtlCompareMemoryUlong</b> must be running at IRQL < DISPATCH_LEVEL. 

For more information about managing buffered data and initializing driver-allocated buffers, see <a href="/windows-hardware/drivers/ddi/index">Buffered Data and Buffer Initialization</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcomparememory">RtlCompareMemory</a>
