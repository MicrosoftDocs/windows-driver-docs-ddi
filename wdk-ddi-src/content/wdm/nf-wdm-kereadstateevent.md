---
UID: NF:wdm.KeReadStateEvent
title: KeReadStateEvent function
author: windows-driver-content
description: The KeReadStateEvent routine returns the current state, signaled or not-signaled, of an event object.
old-location: kernel\kereadstateevent.htm
old-project: kernel
ms.assetid: c80e18db-332a-41d3-b761-46b94436742c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeReadStateEvent, KeReadStateEvent routine [Kernel-Mode Driver Architecture], k105_f0b95771-5c9f-4573-8dc0-44b8f673b6d7.xml, kernel.kereadstateevent, wdm/KeReadStateEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
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
-	KeReadStateEvent
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReadStateEvent function


## -description


The <b>KeReadStateEvent</b> routine returns the current state, signaled or not-signaled, of an event object.


## -syntax


````
LONG KeReadStateEvent(
  _In_ PRKEVENT Event
);
````


## -parameters




### -param Event [in]

A pointer to an initialized event object for which the caller provides the storage.


## -returns



If the event object is currently set to a signaled state, a nonzero value is returned. Otherwise, zero is returned.




## -remarks



This routine provides an efficient way to poll the signal state of an event. <b>KeReadStateEvent</b> reads the state of the event without synchronizing its access to the event. Do not assume that accesses of an event state by <b>KeReadStateEvent</b> are mutually exclusive of accesses by routines, such as <a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a> and <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>, that do synchronize their access to the event state.

It is also possible to read the state of an event from a driver's interrupt service routine at DIRQL, if the following conditions are met: the driver's event object is resident (probably in its device extension), and any other function that accesses the event synchronizes its access with the ISR.

For more information about event objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>.




## -see-also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>



<a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>



<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>



<a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a>



<a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReadStateEvent routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

