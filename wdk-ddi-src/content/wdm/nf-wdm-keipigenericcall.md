---
UID: NF:wdm.KeIpiGenericCall
title: KeIpiGenericCall function
description: The KeIpiGenericCall routine causes the specified routine to run on all processors simultaneously.
old-location: kernel\keipigenericcall.htm
tech.root: kernel
ms.assetid: 11424e94-d279-4003-a97c-a46d1a75e8e5
ms.date: 04/30/2018
ms.keywords: KeIpiGenericCall, KeIpiGenericCall routine [Kernel-Mode Driver Architecture], k105_f819c564-ecbc-4d28-aa64-6936c8ad3542.xml, kernel.keipigenericcall, wdm/KeIpiGenericCall
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
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
req.irql: "< IPI_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeIpiGenericCall
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeIpiGenericCall function


## -description


The <b>KeIpiGenericCall</b> routine causes the specified routine to run on all processors simultaneously.


## -parameters




### -param BroadcastFunction [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550688">IpiGenericCall</a> routine. This routine is run on every processor simultaneously.


### -param Context [in]

Specifies the value to pass to <i>IpiGenericCall</i> when it is called. 


## -returns



<b>KeIpiGenericCall</b> returns the value that <a href="https://msdn.microsoft.com/library/windows/hardware/ff550688">IpiGenericCall</a> returns on the source processor (the processor that called <b>KeIpiGenericCall</b>). 




## -remarks



When a driver calls <b>KeIpiGenericCall</b>, the system interrupts every processor and raises the IRQL to IPI_LEVEL (interprocessor interrupt level). Each processor spins on a barrier until all processors have reached the barrier; then, all processors begin calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550688">IpiGenericCall</a>. <b>KeIpiGenericCall</b> waits for all calls to <i>IpiGenericCall</i> to complete before returning. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550688">IpiGenericCall</a>
 

 

