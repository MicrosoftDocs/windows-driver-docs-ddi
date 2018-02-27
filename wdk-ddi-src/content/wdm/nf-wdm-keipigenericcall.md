---
UID: NF:wdm.KeIpiGenericCall
title: KeIpiGenericCall function
author: windows-driver-content
description: The KeIpiGenericCall routine causes the specified routine to run on all processors simultaneously.
old-location: kernel\keipigenericcall.htm
old-project: kernel
ms.assetid: 11424e94-d279-4003-a97c-a46d1a75e8e5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeIpiGenericCall, KeIpiGenericCall routine [Kernel-Mode Driver Architecture], k105_f819c564-ecbc-4d28-aa64-6936c8ad3542.xml, kernel.keipigenericcall, wdm/KeIpiGenericCall
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeIpiGenericCall function


## -description


The <b>KeIpiGenericCall</b> routine causes the specified routine to run on all processors simultaneously.


## -syntax


````
ULONG_PTR KeIpiGenericCall(
  _In_ PKIPI_BROADCAST_WORKER BroadcastFunction,
  _In_ ULONG_PTR              Context
);
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeIpiGenericCall routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

