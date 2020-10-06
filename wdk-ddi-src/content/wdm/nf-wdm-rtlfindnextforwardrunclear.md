---
UID: NF:wdm.RtlFindNextForwardRunClear
title: RtlFindNextForwardRunClear function (wdm.h)
description: The RtlFindNextForwardRunClear routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindnextforwardrunclear.htm
tech.root: kernel
ms.assetid: d923c1a4-4715-4632-8c75-0e48dda9a210
ms.date: 04/30/2018
keywords: ["RtlFindNextForwardRunClear function"]
ms.keywords: RtlFindNextForwardRunClear, RtlFindNextForwardRunClear routine [Kernel-Mode Driver Architecture], k109_3625ede2-f1b5-495d-9b79-2063e0daa567.xml, kernel.rtlfindnextforwardrunclear, wdm/RtlFindNextForwardRunClear
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFindNextForwardRunClear
 - wdm/RtlFindNextForwardRunClear
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFindNextForwardRunClear
---

# RtlFindNextForwardRunClear function


## -description

The <b>RtlFindNextForwardRunClear</b> routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position.

## -parameters

### -param BitMapHeader 

[in]
A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine.

### -param FromIndex 

[in]
Specifies a zero-based bit position at which to start looking for a clear run of bits.

### -param StartingRunIndex 

[out]
Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run. Its value is meaningless if <b>RtlFindNextForwardRunClear</b> cannot find a run of clear bits.

## -returns

<b>RtlFindNextForwardRunClear</b> returns either the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits following <i>FromIndex</i> in the bitmap.

## -remarks

Callers of <b>RtlFindNextForwardRunClear</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindNextForwardRunClear</b> can be called at any IRQL.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbits">RtlFindClearBits</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearruns">RtlFindClearRuns</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear">RtlFindFirstRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear">RtlFindLongestRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>