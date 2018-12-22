---
UID: NF:wdm.KeClearEvent
title: KeClearEvent function
description: The KeClearEvent routine sets an event to a not-signaled state.
old-location: kernel\keclearevent.htm
tech.root: kernel
ms.assetid: ded54c88-3da0-42ec-88be-865d3cb87651
ms.date: 04/30/2018
ms.keywords: KeClearEvent, KeClearEvent routine [Kernel-Mode Driver Architecture], k105_1ea5c68a-0b59-48ec-911b-058b6a3e586b.xml, kernel.keclearevent, wdm/KeClearEvent
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoBuildDeviceIoControlSetEvent, IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeClearEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeClearEvent function


## -description


The <b>KeClearEvent</b> routine sets an event to a not-signaled state. 


## -parameters




### -param Event [in, out]

Pointer to an initialized dispatcher object of type event for which the caller supplies the storage. 


## -returns



None




## -remarks



<i>Event</i> is set to a not-signaled state, meaning its value is set to zero.

For better performance, use <b>KeClearEvent</b> unless the caller uses the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff553176">KeResetEvent</a> to determine what to do next.

For more information about event objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553089">KeReadStateEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553176">KeResetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553253">KeSetEvent</a>
 

 

