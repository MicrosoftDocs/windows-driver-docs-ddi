---
UID: NF:wdm.RtlFindClearBits
title: RtlFindClearBits function (wdm.h)
description: The RtlFindClearBits routine searches for a range of clear bits of a requested size within a bitmap.
old-location: kernel\rtlfindclearbits.htm
tech.root: kernel
ms.assetid: 5279d126-8fd3-43dd-be03-2134e46a3ef9
ms.date: 04/30/2018
ms.keywords: RtlFindClearBits, RtlFindClearBits routine [Kernel-Mode Driver Architecture], k109_bf520772-12d8-403e-8b57-31a24e9a27b6.xml, kernel.rtlfindclearbits, wdm/RtlFindClearBits
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlFindClearBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindClearBits function


## -description


The <b>RtlFindClearBits</b> routine searches for a range of clear bits of a requested size within a bitmap. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


### -param NumberToFind [in]

Specifies how many contiguous clear bits will satisfy this request. 


### -param HintIndex [in]

Specifies a zero-based bit position from which to start looking for a clear bit range of the given size. 


## -returns



<b>RtlFindClearBits</b> either returns the zero-based starting bit index for a clear bit range of at least the requested size, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap. 




## -remarks



For a successful call, the returned bit position is not necessarily equivalent to the given <i>HintIndex</i>. If necessary, <b>RtlFindClearBits</b> searches the whole bitmap to locate a clear bit range of the requested size. However, it starts searching for the requested range from <i>HintIndex</i>, so callers can find such a range more quickly when they can supply appropriate hints about where to start looking. 

Callers of <b>RtlFindClearBits</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindClearBits</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561874">RtlFindClearBitsAndSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561890">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562034">RtlNumberOfClearBits</a>
 

 

