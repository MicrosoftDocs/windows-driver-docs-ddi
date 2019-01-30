---
UID: NF:wdm.RtlNumberOfSetBits
title: RtlNumberOfSetBits function (wdm.h)
description: The RtlNumberOfSetBits routine returns a count of the set bits in a given bitmap variable.
old-location: kernel\rtlnumberofsetbits.htm
tech.root: kernel
ms.assetid: 6208f750-4871-43b9-b848-011180d39fd8
ms.date: 04/30/2018
ms.keywords: RtlNumberOfSetBits, RtlNumberOfSetBits routine [Kernel-Mode Driver Architecture], k109_b8b2c3f8-3ec3-4690-90bb-e5b120b5b062.xml, kernel.rtlnumberofsetbits, wdm/RtlNumberOfSetBits
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlNumberOfSetBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlNumberOfSetBits function


## -description


The <b>RtlNumberOfSetBits</b> routine returns a count of the set bits in a given bitmap variable. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. 


## -returns



<b>RtlNumberOfSetBits</b> returns a count of the bits that are currently set. 




## -remarks



Callers of <b>RtlNumberOfSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfSetBits</b> can be called at any IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561890">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562034">RtlNumberOfClearBits</a>
 

 

