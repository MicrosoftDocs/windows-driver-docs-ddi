---
UID: NF:wdm.RtlTestBit
title: RtlTestBit function (wdm.h)
description: The RtlTestBit routine returns the value of a bit in a bitmap.
old-location: kernel\rtltestbit.htm
tech.root: kernel
ms.assetid: 52f892a8-e82d-465d-aef5-630f5e971e8f
ms.date: 04/30/2018
ms.keywords: RtlTestBit, RtlTestBit routine [Kernel-Mode Driver Architecture], k109_552764bc-c69d-4039-8284-8cc8f41dc16a.xml, kernel.rtltestbit, wdm/RtlTestBit
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlTestBit
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlTestBit function


## -description


The <b>RtlTestBit</b> routine returns the value of a bit in a bitmap. 


## -parameters




### -param BitMapHeader [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


### -param BitNumber [in]

Specifies the zero-based index of the bit within the bitmap. The routine returns the value of this bit. 


## -returns



<b>RtlTestBit</b> returns the value of the bit that the <i>BitNumber</i> parameter points to. 




## -remarks



Callers of <b>RtlTestBit</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlTestBit</b> can be called at any IRQL. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>
 

 

