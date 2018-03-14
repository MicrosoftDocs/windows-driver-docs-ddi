---
UID: NF:wdm.IoCreateNotificationEvent
title: IoCreateNotificationEvent function
author: windows-driver-content
description: The IoCreateNotificationEvent routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred.
old-location: kernel\iocreatenotificationevent.htm
old-project: kernel
ms.assetid: 44be034e-0c82-4980-a246-132d1b50dee1
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoCreateNotificationEvent, IoCreateNotificationEvent routine [Kernel-Mode Driver Architecture], k104_2b3bf223-0427-40e2-9f95-da5aa12c5da2.xml, kernel.iocreatenotificationevent, wdm/IoCreateNotificationEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCreateNotificationEvent
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCreateNotificationEvent function


## -description


The <b>IoCreateNotificationEvent</b> routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred. 


## -syntax


````
PKEVENT IoCreateNotificationEvent(
  _In_  PUNICODE_STRING EventName,
  _Out_ PHANDLE         EventHandle
);
````


## -parameters




### -param EventName [in]

Pointer to a buffer containing a null-terminated Unicode string that names the event.


### -param EventHandle [out]

Pointer to a location in which to return a handle for the event object. In Windows Server 2003 and later versions of Windows, the returned handle is a <a href="https://msdn.microsoft.com/4015d7bd-48f6-489b-a0e5-eca83758c5bb">kernel handle</a>. 


## -returns



<b>IoCreateNotificationEvent</b> returns a pointer to the created or opened event object or <b>NULL</b> if the event object could not be created or opened. 




## -remarks



<b>IoCreateNotificationEvent</b> creates and opens the event object if it does not already exist. <b>IoCreateNotificationEvent</b> sets the state of a new notification event to Signaled. If the event object already exists, <b>IoCreateNotificationEvent</b> just opens the event object.

When a notification event is set to the Signaled state it remains in that state until it is explicitly cleared.

Notification events, like synchronization events, are used to coordinate execution. Unlike a synchronization event, a notification event is not auto-resetting. Once a notification event is in the Signaled state, it remains in that state until it is explicitly reset (with a call to <a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a> or <a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>).

To synchronize on a notification event:

<ol>
<li>
Open the notification event with <b>IoCreateNotificationEvent</b>. Identify the event with the <i>EventName</i> string.

</li>
<li>
Wait for the event to be signaled by calling <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a> with the PKEVENT returned by <b>IoCreateNotificationEvent</b>. More than one thread of execution can wait for a given notification event. To poll instead of stall, specify a <i>Timeout</i> of zero to <b>KeWaitForSingleObject</b>.

</li>
<li>
Close the handle to the notification event with <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> when access to the event is no longer needed. 

</li>
</ol>
Sharing event objects between user mode and kernel mode requires care. There are two main methods for sharing event objects: 

<ul>
<li>
The user-mode application creates the event object and passes a handle to the object to the driver by sending an IOCTL to the driver. The driver must handle the IOCTL in the context of the process that created the event object and must validate the handle by calling <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>. This method is the recommended method for sharing event objects between user and kernel modes.

</li>
<li>
The driver creates a named event object in the \\BaseNamedObjects object directory. You can open a kernel-mode event named \\BaseNamedObjects\<i>Xxx</i> in user mode under the name <i>Xxx</i>. Note that security settings can prevent an application from opening the event. For more information, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70044">OpenEvent Fails in a Non-Administrator Account</a> KB article. The \\BaseNamedObjects object directory is not created until the Microsoft Win32 subsystem initializes, so drivers that are loaded at boot time cannot create event objects in the \\BaseNamedObjects directory in their <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routines.

</li>
</ul>
For more information about events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>. 




## -see-also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>



<a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a>



<a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wdm\nf-wdm-iocreatesynchronizationevent.md">IoCreateSynchronizationEvent</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCreateNotificationEvent routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

