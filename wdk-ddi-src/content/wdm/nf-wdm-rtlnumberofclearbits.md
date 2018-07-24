---
UID: NF:wdm.RtlNumberOfClearBits
title: RtlNumberOfClearBits function
author: windows-driver-content
description: The RtlNumberOfClearBits routine returns a count of the clear bits in a given bitmap variable.
old-location: kernel\rtlnumberofclearbits.htm
tech.root: kernel
ms.assetid: 739dc01d-7340-449f-8fe6-64e5c8284436
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlNumberOfClearBits, RtlNumberOfClearBits routine [Kernel-Mode Driver Architecture], k109_1b655b45-806c-4199-91e6-2ed2f4d4e570.xml, kernel.rtlnumberofclearbits, wdm/RtlNumberOfClearBits
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
-	RtlNumberOfClearBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlNumberOfClearBits function


## -description


The <b>RtlNumberOfClearBits</b> routine returns a count of the clear bits in a given bitmap variable. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


## -returns



<b>RtlNumberOfClearBits</b> returns the number of bits that are currently clear. 




## -remarks



Callers of <b>RtlNumberOfClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfClearBits</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561875">RtlFindClearRuns</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562037">RtlNumberOfSetBits</a>
 

 

