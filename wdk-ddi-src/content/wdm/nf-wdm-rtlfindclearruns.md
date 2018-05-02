---
UID: NF:wdm.RtlFindClearRuns
title: RtlFindClearRuns function
author: windows-driver-content
description: The RtlFindClearRuns routine finds the specified number of runs of clear bits within a given bitmap.
old-location: kernel\rtlfindclearruns.htm
old-project: kernel
ms.assetid: ad44c7ba-1d8e-4ba4-8d1b-83ff8b2e3d06
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlFindClearRuns, RtlFindClearRuns routine [Kernel-Mode Driver Architecture], k109_10c01954-483b-4ec8-a54d-50928663dc16.xml, kernel.rtlfindclearruns, wdm/RtlFindClearRuns
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
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFindClearRuns
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindClearRuns function


## -description


The <b>RtlFindClearRuns</b> routine finds the specified number of runs of clear bits within a given bitmap.


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


### -param RunArray [out]

Pointer to the first element in a caller-allocated array for the bit position and length of each clear run found in the given bitmap variable. 


### -param SizeOfRunArray [in]

Specifies the maximum number of clear runs to satisfy this request.


### -param LocateLongestRuns [in]

If <b>TRUE</b>, specifies that the routine is to search the entire bitmap for the longest clear runs it can find. Otherwise, the routine stops searching when it has found the number of clear runs specified by <i>SizeOfRunArray</i>. 


## -returns



<b>RtlFindClearRuns</b> returns the number of clear runs found.




## -remarks



If <i>LocateLongestRuns </i>is <b>TRUE</b>, the clear runs indicated at <i>RunArray </i>are sorted from longest to shortest. A clear run can consist of a single bit.

Callers of <b>RtlFindClearRuns</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindClearRuns</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>
 

 

