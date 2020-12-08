---
UID: NF:wdm.RtlFindClearRuns
title: RtlFindClearRuns function (wdm.h)
description: The RtlFindClearRuns routine finds the specified number of runs of clear bits within a given bitmap.
old-location: kernel\rtlfindclearruns.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlFindClearRuns function"]
ms.keywords: RtlFindClearRuns, RtlFindClearRuns routine [Kernel-Mode Driver Architecture], k109_10c01954-483b-4ec8-a54d-50928663dc16.xml, kernel.rtlfindclearruns, wdm/RtlFindClearRuns
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
 - RtlFindClearRuns
 - wdm/RtlFindClearRuns
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFindClearRuns
---

# RtlFindClearRuns function


## -description

The <b>RtlFindClearRuns</b> routine finds the specified number of runs of clear bits within a given bitmap.

## -parameters

### -param BitMapHeader 

[in]
A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine.

### -param RunArray 

[out]
Pointer to the first element in a caller-allocated array for the bit position and length of each clear run found in the given bitmap variable.

### -param SizeOfRunArray 

[in]
Specifies the maximum number of clear runs to satisfy this request.

### -param LocateLongestRuns 

[in]
If <b>TRUE</b>, specifies that the routine is to search the entire bitmap for the longest clear runs it can find. Otherwise, the routine stops searching when it has found the number of clear runs specified by <i>SizeOfRunArray</i>.

## -returns

<b>RtlFindClearRuns</b> returns the number of clear runs found.

## -remarks

If <i>LocateLongestRuns </i>is <b>TRUE</b>, the clear runs indicated at <i>RunArray </i>are sorted from longest to shortest. A clear run can consist of a single bit.

Callers of <b>RtlFindClearRuns</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindClearRuns</b> can be called at any IRQL.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbits">RtlFindClearBits</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear">RtlFindFirstRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear">RtlFindLongestRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>
