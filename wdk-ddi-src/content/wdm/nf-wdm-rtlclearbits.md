---
UID: NF:wdm.RtlClearBits
title: RtlClearBits function
author: windows-driver-content
description: The RtlClearBits routine sets all bits in the specified range of bits in the bitmap to zero.
old-location: kernel\rtlclearbits.htm
old-project: kernel
ms.assetid: 2c332700-7778-4342-b99b-093142496624
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlClearBits, RtlClearBits routine [Kernel-Mode Driver Architecture], k109_ee20da99-4d30-46dc-99c1-d3d8dfa92d08.xml, kernel.rtlclearbits, wdm/RtlClearBits
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
req.irql: "<= APC_LEVEL (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlClearBits
product: Windows
targetos: Windows
req.typenames: 
---

# RtlClearBits function


## -description


The <b>RtlClearBits</b> routine sets all bits in the specified range of bits in the bitmap to zero.


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.


### -param StartingIndex [in]

The index of the first bit in the bit range that is to be cleared. If the bitmap contains N bits, the bits are numbered from 0 to N-1.


### -param NumberToClear [in]

Specifies how many bits to clear. If the bitmap contains N bits, this parameter can be a value in the range 1 to (N - <i>StartingIndex</i>).


## -returns



This routine does not return a value.




## -remarks



If the <i>NumberToClear</i> parameter is zero, <b>RtlClearBits</b> simply returns control without clearing any bits.

The sum (<i>StartingIndex</i> + <i>NumberToClear</i>) must not exceed the <i>SizeOfBitMap</i> parameter value specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> call that initialized the bitmap.

Callers of <b>RtlClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearBits</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561745">RtlAreBitsSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561755">RtlClearAllBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561890">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561895">RtlFindSetBitsAndClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562037">RtlNumberOfSetBits</a>
 

 

