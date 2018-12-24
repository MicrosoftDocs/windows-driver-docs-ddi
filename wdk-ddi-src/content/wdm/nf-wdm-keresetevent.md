---
UID: NF:wdm.KeResetEvent
title: KeResetEvent function
description: The KeResetEvent routine resets a specified event object to a not-signaled state and returns the previous state of that event object.
old-location: kernel\keresetevent.htm
tech.root: kernel
ms.assetid: 90be986b-e63e-4ae3-a0f3-87f6f58583dc
ms.date: 04/30/2018
ms.keywords: KeResetEvent, KeResetEvent routine [Kernel-Mode Driver Architecture], k105_d2a27b37-56af-46a4-8a48-da507261f77a.xml, kernel.keresetevent, wdm/KeResetEvent
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeResetEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeResetEvent function


## -description


The <b>KeResetEvent</b> routine resets a specified event object to a not-signaled state and returns the previous state of that event object.


## -parameters




### -param Event [in, out]

A pointer to an initialized dispatcher object of type event for which the caller provides the storage. 


## -returns



<b>KeResetEvent</b> returns a value that indicates the previous state of the specified <i>Event</i>, which is nonzero for a signaled state. 




## -remarks



<i>Event</i> is reset to a not-signaled state, meaning that its value is set to zero.

Unless the caller requires the value that is returned by <b>KeResetEvent</b>, using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551980">KeClearEvent</a> routine is a faster way to set an event object to a not-signaled state.

For more information about event objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551980">KeClearEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553089">KeReadStateEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553253">KeSetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

