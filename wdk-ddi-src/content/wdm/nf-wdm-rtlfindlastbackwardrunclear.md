---
UID: NF:wdm.RtlFindLastBackwardRunClear
title: RtlFindLastBackwardRunClear function (wdm.h)
description: The RtlFindLastBackwardRunClear routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindlastbackwardrunclear.htm
tech.root: kernel
ms.assetid: ad1a6c18-b0c5-4289-9eec-2b8c8d8d2f07
ms.date: 04/30/2018
keywords: ["RtlFindLastBackwardRunClear function"]
ms.keywords: RtlFindLastBackwardRunClear, RtlFindLastBackwardRunClear routine [Kernel-Mode Driver Architecture], k109_b7075a86-ffa4-4a6a-98fb-60848c037253.xml, kernel.rtlfindlastbackwardrunclear, wdm/RtlFindLastBackwardRunClear
f1_keywords:
 - "wdm/RtlFindLastBackwardRunClear"
 - "RtlFindLastBackwardRunClear"
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
req.irql: <= APC_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlFindLastBackwardRunClear
targetos: Windows
req.typenames: 
---

# RtlFindLastBackwardRunClear function


## -description


The <b>RtlFindLastBackwardRunClear</b> routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.


## -parameters




### -param BitMapHeader 
[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


### -param FromIndex 
[in]
Specifies a zero-based bit position at which to start looking for a clear run of bits.


### -param StartingRunIndex 
[out]
Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run preceding the given <i>FromIndex</i>. Its value is meaningless if <b>RtlFindLastBackwardRunClear</b> cannot find a run of clear bits. 


## -returns



<b>RtlFindLastBackwardRunClear</b> returns the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits preceding <i>FromIndex</i> in the bitmap.




## -remarks




Callers of <b>RtlFindLastBackwardRunClear</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindLastBackwardRunClear</b> can be called at any IRQL. 




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
 

 

