---
UID: NF:wdm.IoCreateNotificationEvent
title: IoCreateNotificationEvent function (wdm.h)
description: The IoCreateNotificationEvent routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred.
old-location: kernel\iocreatenotificationevent.htm
tech.root: kernel
ms.date: 10/20/2020
keywords: ["IoCreateNotificationEvent function"]
ms.keywords: IoCreateNotificationEvent, IoCreateNotificationEvent routine [Kernel-Mode Driver Architecture], k104_2b3bf223-0427-40e2-9f95-da5aa12c5da2.xml, kernel.iocreatenotificationevent, wdm/IoCreateNotificationEvent
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCreateNotificationEvent
 - wdm/IoCreateNotificationEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateNotificationEvent
---

# IoCreateNotificationEvent function


## -description

The <b>IoCreateNotificationEvent</b> routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred.

## -parameters

### -param EventName 

[in]
Pointer to a buffer containing a null-terminated Unicode string that names the event.

### -param EventHandle 

[out]
Pointer to a location in which to return a kernel handle for the event object.

## -returns

<b>IoCreateNotificationEvent</b> returns a pointer to the created or opened event object or <b>NULL</b> if the event object could not be created or opened.

## -remarks

If the event object does not already exist, <b>IoCreateNotificationEvent</b> creates and opens it, and sets its state to Signaled.

If the event object already exists, <b>IoCreateNotificationEvent</b> just opens the event object.

Both notification events and synchronization events are used to coordinate execution. However, while a synchronization event resets itself, a notification event remains in the Signaled state until the driver calls [**KeClearEvent**](./nf-wdm-keclearevent.md) or [**KeResetEvent**](./nf-wdm-keresetevent.md).

To synchronize on a notification event:

1. Open the notification event with **IoCreateNotificationEvent**. Identify the event with the *EventName* string.
2. Wait for the event to be signaled by calling [**KeWaitForSingleObject**](./nf-wdm-kewaitforsingleobject.md) with the PKEVENT returned by **IoCreateNotificationEvent**. More than one thread of execution can wait for a given notification event. To poll instead of stall, specify a *Timeout* of zero to **KeWaitForSingleObject**.
3. Close the handle to the notification event with [**ZwClose**](../ntifs/nf-ntifs-ntclose.md) when access to the event is no longer needed. 

There are two main methods for sharing event objects: 

* The user-mode application creates the event object and passes a handle to the object to the driver by sending an IOCTL to the driver. The driver must handle the IOCTL in the context of the process that created the event object and must validate the handle by calling [**ObReferenceObjectByHandle**](./nf-wdm-obreferenceobjectbyhandle.md). This method is the recommended method for sharing event objects between user and kernel modes.

* The driver creates a named event object in the global `\BaseNamedObjects` object directory. To access a kernel-mode event from user-mode, use the name `Global\\`*Xxx*. Note that security settings can prevent an application from opening the event. The `\\BaseNamedObjects` object directory is not created until the Microsoft Win32 subsystem initializes, so drivers that are loaded at boot time cannot create event objects in the `\\BaseNamedObjects` directory in their [*DriverEntry*](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routines.

For more information about events, see [Event Objects](/windows-hardware/drivers/kernel/event-objects).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>
