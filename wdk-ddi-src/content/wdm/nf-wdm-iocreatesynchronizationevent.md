---
UID: NF:wdm.IoCreateSynchronizationEvent
title: IoCreateSynchronizationEvent function (wdm.h)
description: The IoCreateSynchronizationEvent routine creates or opens a named synchronization event for use in serialization of access to hardware between two otherwise unrelated drivers.
old-location: kernel\iocreatesynchronizationevent.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoCreateSynchronizationEvent function"]
ms.keywords: IoCreateSynchronizationEvent, IoCreateSynchronizationEvent routine [Kernel-Mode Driver Architecture], k104_413cbfff-08a2-44b5-acdc-0e23d382a3d3.xml, kernel.iocreatesynchronizationevent, wdm/IoCreateSynchronizationEvent
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
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
 - IoCreateSynchronizationEvent
 - wdm/IoCreateSynchronizationEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateSynchronizationEvent
---

# IoCreateSynchronizationEvent function


## -description

The <b>IoCreateSynchronizationEvent</b> routine creates or opens a named synchronization event for use in serialization of access to hardware between two otherwise unrelated drivers.

## -parameters

### -param EventName [in]


Pointer to a buffer containing a null-terminated Unicode string that names the event.

### -param EventHandle [out]


Pointer to a location in which to return a handle for the event object. In Windows Server 2003 and later versions of Windows, the returned handle is a <a href="/windows-hardware/drivers/">kernel handle</a>.

## -returns

<b>IoCreateSynchronizationEvent</b> returns a pointer to the created or opened event object or <b>NULL</b> if the event object could not be created or opened.

## -remarks

The event object is created if it does not already exist. <b>IoCreateSynchronizationEvent</b> sets the state of a new synchronization event to Signaled. If the event object already exists, it is simply opened. The pair of drivers that use a synchronization event call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a> with the PKEVENT pointer returned by this routine.

When a synchronization event is set to the Signaled state, a single thread of execution that was waiting for the event is released, and the event is automatically reset to the Not-Signaled state.

To release the event, a driver calls <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> with the event handle.

Sharing event objects between user mode and kernel mode requires care. There are two main methods for sharing event objects: 

* The user-mode application creates the event object and passes a handle to the object to the driver by sending an IOCTL to the driver. The driver must handle the IOCTL in the context of the process that created the event object and must validate the handle by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbyhandle">ObReferenceObjectByHandle</a>. This method is the recommended method for sharing event objects between user and kernel modes.

* The driver creates a named event object in the global `\BaseNamedObjects` object directory. To access a kernel-mode event from user-mode, use the name `Global\\`*Xxx*. Note that security settings can prevent an application from opening the event. The \\BaseNamedObjects object directory is not created until the Microsoft Win32 subsystem initializes, so drivers that are loaded at boot time cannot create event objects in the \\BaseNamedObjects directory in their <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routines

For more information about events, see <a href="/windows-hardware/drivers/kernel/event-objects">Event Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatenotificationevent">IoCreateNotificationEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring">RtlInitUnicodeString</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>
