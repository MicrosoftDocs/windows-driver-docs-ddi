---
UID: NF:wdm.RtlFindFirstRunClear
title: RtlFindFirstRunClear function (wdm.h)
description: The RtlFindFirstRunClear routine searches for the initial contiguous range of clear bits within a given bitmap.
old-location: kernel\rtlfindfirstrunclear.htm
tech.root: kernel
ms.assetid: 21e7e65c-b549-4997-b6dd-a95577edaa26
ms.date: 04/30/2018
keywords: ["RtlFindFirstRunClear function"]
ms.keywords: RtlFindFirstRunClear, RtlFindFirstRunClear routine [Kernel-Mode Driver Architecture], k109_9ccc7e63-f136-4625-83c1-bf38a534307e.xml, kernel.rtlfindfirstrunclear, wdm/RtlFindFirstRunClear
f1_keywords:
 - "wdm/RtlFindFirstRunClear"
 - "RtlFindFirstRunClear"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlFindFirstRunClear
targetos: Windows
req.typenames: 
---

# RtlFindFirstRunClear function


## -description


The <b>RtlFindFirstRunClear</b> routine searches for the initial contiguous range of clear bits within a given bitmap. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


### -param StartingIndex [out]

Pointer to a variable in which the starting index of the initial clear run in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the returned range. Its value is meaningless if <b>RtlFindFirstRunClear</b> cannot find a run of clear bits. 


## -returns



<b>RtlFindFirstRunClear</b> returns either the number of bits in the run beginning at <i>StartingIndex</i>, or zero if it cannot find a run of clear bits within the bitmap. 




## -remarks



A returned run can have a single clear bit. That is, once a clear bit is found, <b>RtlFindFirstRunClear</b> continues searching until it finds the next set bit, and then returns the number of clear bits in the run it found.

Callers of <b>RtlFindFirstRunClear</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindFirstRunClear</b> can be called at any IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbits">RtlFindClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearruns">RtlFindClearRuns</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear">RtlFindFirstRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear">RtlFindLongestRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofclearbits">RtlNumberOfClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetbits">RtlSetBits</a>
 

 

