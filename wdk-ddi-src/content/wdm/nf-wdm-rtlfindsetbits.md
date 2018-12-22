---
UID: NF:wdm.RtlFindSetBits
title: RtlFindSetBits function
description: The RtlFindSetBits routine searches for a range of set bits of a requested size within a bitmap.
old-location: kernel\rtlfindsetbits.htm
tech.root: kernel
ms.assetid: 35add921-e5a2-4c18-83db-86150c43b034
ms.date: 04/30/2018
ms.keywords: RtlFindSetBits, RtlFindSetBits routine [Kernel-Mode Driver Architecture], k109_67665139-638f-4dc5-b0b4-db3782c1f294.xml, kernel.rtlfindsetbits, wdm/RtlFindSetBits
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
-	RtlFindSetBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindSetBits function


## -description


The <b>RtlFindSetBits</b> routine searches for a range of set bits of a requested size within a bitmap. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


### -param NumberToFind [in]

Specifies how many contiguous set bits will satisfy this request. 


### -param HintIndex [in]

Specifies a zero-based bit position around which to start looking for a set bit range of the given size. 


## -returns



<b>RtlFindSetBits</b> either returns the zero-based starting bit index for a set bit range of the requested size, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap variable. 




## -remarks



For a successful call, the returned bit position is not necessarily equivalent to the given <i>HintIndex</i>. If necessary, <b>RtlFindSetBits</b> searches the whole bitmap to locate a set bit range of the requested size. However, it starts searching for the requested range near <i>HintIndex</i>, so callers can find such a range more quickly when they can supply appropriate hints about where to start looking. 

Callers of <b>RtlFindSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindSetBits</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561745">RtlAreBitsSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561763">RtlClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561895">RtlFindSetBitsAndClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562037">RtlNumberOfSetBits</a>
 

 

