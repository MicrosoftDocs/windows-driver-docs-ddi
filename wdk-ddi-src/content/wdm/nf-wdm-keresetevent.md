---
UID: NF:wdm.KeResetEvent
title: KeResetEvent function (wdm.h)
description: The KeResetEvent routine resets a specified event object to a not-signaled state and returns the previous state of that event object.
old-location: kernel\keresetevent.htm
tech.root: kernel
ms.assetid: 90be986b-e63e-4ae3-a0f3-87f6f58583dc
ms.date: 04/30/2018
keywords: ["KeResetEvent function"]
ms.keywords: KeResetEvent, KeResetEvent routine [Kernel-Mode Driver Architecture], k105_d2a27b37-56af-46a4-8a48-da507261f77a.xml, kernel.keresetevent, wdm/KeResetEvent
f1_keywords:
 - "wdm/KeResetEvent"
 - "KeResetEvent"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeResetEvent
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

Unless the caller requires the value that is returned by <b>KeResetEvent</b>, using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a> routine is a faster way to set an event object to a not-signaled state.

For more information about event objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/event-objects">Event Objects</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstateevent">KeReadStateEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
 

 

