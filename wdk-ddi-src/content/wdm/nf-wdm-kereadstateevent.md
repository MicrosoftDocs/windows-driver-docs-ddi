---
UID: NF:wdm.KeReadStateEvent
title: KeReadStateEvent function (wdm.h)
description: The KeReadStateEvent routine returns the current state, signaled or not-signaled, of an event object.
old-location: kernel\kereadstateevent.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeReadStateEvent function"]
ms.keywords: KeReadStateEvent, KeReadStateEvent routine [Kernel-Mode Driver Architecture], k105_f0b95771-5c9f-4573-8dc0-44b8f673b6d7.xml, kernel.kereadstateevent, wdm/KeReadStateEvent
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReadStateEvent
 - wdm/KeReadStateEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReadStateEvent
---

# KeReadStateEvent function


## -description

The <b>KeReadStateEvent</b> routine returns the current state, signaled or not-signaled, of an event object.

## -parameters

### -param Event [in]


A pointer to an initialized event object for which the caller provides the storage.

## -returns

If the event object is currently set to a signaled state, a nonzero value is returned. Otherwise, zero is returned.

## -remarks

This routine provides an efficient way to poll the signal state of an event. <b>KeReadStateEvent</b> reads the state of the event without synchronizing its access to the event. Do not assume that accesses of an event state by <b>KeReadStateEvent</b> are mutually exclusive of accesses by routines, such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>, that do synchronize their access to the event state.

It is also possible to read the state of an event from a driver's interrupt service routine at DIRQL, if the following conditions are met: the driver's event object is resident (probably in its device extension), and any other function that accesses the event synchronizes its access with the ISR.

For more information about event objects, see <a href="/windows-hardware/drivers/kernel/event-objects">Event Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>
