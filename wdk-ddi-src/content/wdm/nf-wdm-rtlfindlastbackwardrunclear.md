---
UID: NF:wdm.RtlFindLastBackwardRunClear
title: RtlFindLastBackwardRunClear function
author: windows-driver-content
description: The RtlFindLastBackwardRunClear routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindlastbackwardrunclear.htm
tech.root: kernel
ms.assetid: ad1a6c18-b0c5-4289-9eec-2b8c8d8d2f07
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlFindLastBackwardRunClear, RtlFindLastBackwardRunClear routine [Kernel-Mode Driver Architecture], k109_b7075a86-ffa4-4a6a-98fb-60848c037253.xml, kernel.rtlfindlastbackwardrunclear, wdm/RtlFindLastBackwardRunClear
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFindLastBackwardRunClear
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindLastBackwardRunClear function


## -description


The <b>RtlFindLastBackwardRunClear</b> routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position.


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


### -param FromIndex [in]

Specifies a zero-based bit position at which to start looking for a clear run of bits.


### -param StartingRunIndex [out]

Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run preceding the given <i>FromIndex</i>. Its value is meaningless if <b>RtlFindLastBackwardRunClear</b> cannot find a run of clear bits. 


## -returns



<b>RtlFindLastBackwardRunClear</b> returns the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits preceding <i>FromIndex</i> in the bitmap.




## -remarks



On checked builds of Windows Vista and earlier versions of Windows, the internal implementation of the <b>RtlFindLastBackwardRunClear</b> routine can fail a bogus assertion if the caller is running at IRQL = DISPATCH_LEVEL. The failure of this assertion is harmless and can safely be ignored.

Callers of <b>RtlFindLastBackwardRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindLastBackwardRunClear</b> can be called at any IRQL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561875">RtlFindClearRuns</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>
 

 

