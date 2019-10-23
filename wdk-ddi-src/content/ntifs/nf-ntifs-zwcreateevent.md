---
UID: NF:ntifs.ZwCreateEvent
title: ZwCreateEvent function (ntifs.h)
description: The ZwCreateEvent routine creates an event object, sets the initial state of the event to the specified value, and opens a handle to the object with the specified desired access.
old-location: kernel\zwcreateevent.htm
tech.root: kernel
ms.assetid: c11265fb-df9d-405e-ac9f-e868ab392e7b
ms.date: 04/30/2018
ms.keywords: NtCreateEvent, ZwCreateEvent, ZwCreateEvent routine [Kernel-Mode Driver Architecture], k111_53554a99-3112-4f70-8c00-9d632a74d15b.xml, kernel.zwcreateevent, ntifs/NtCreateEvent, ntifs/ZwCreateEvent
ms.topic: function
f1_keywords:
 - "ntifs/ZwCreateEvent"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwCreateEvent
- NtCreateEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwCreateEvent function


## -description


The <b>ZwCreateEvent</b> routine creates an event object, sets the initial state of the event to the specified value, and opens a handle to the object with the specified desired access.


## -parameters




### -param EventHandle [out]

A pointer to a variable that will receive the event object handle. The handle includes bookkeeping information, such as a reference count and security context.


### -param DesiredAccess [in]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that represents the desired types of access for the event object. The following table contains the event-specific ACCESS_MASK values.

<table>
<tr>
<th>Value</th>
<th>Desired access</th>
</tr>
<tr>
<td>EVENT_QUERY_STATE</td>
<td>Query the state of the event object.</td>
</tr>
<tr>
<td>EVENT_MODIFY_STATE</td>
<td>Modify the state of the event object.</td>
</tr>
<tr>
<td>EVENT_ALL_ACCESS</td>
<td>All possible access rights to the event object.</td>
</tr>
</table>
 


### -param ObjectAttributes [in, optional]

A pointer to the object attributes structure supplied by the caller to be used for the specified object. These attributes would include the <b>ObjectName</b> and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>, for example. This parameter is initialized by calling the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> macro.


### -param EventType [in]

The type of the event, which can be <b>SynchronizationEvent</b> or a <b>NotificationEvent</b>. These values belong to the <b>EVENT_TYPE</b> enumeration, which is defined in the Ntdef.h header file.  The event type can be modified with the REALTIME_OBJECT_FLAG modifier to provide priority-ordered queuing of wait requests.


### -param InitialState [in]

The initial state of the event object. Set to <b>TRUE</b> to initialize the event object to the Signaled state. Set to <b>FALSE</b> to initialize the event object to the not-Signaled state.


## -returns



<b>ZwCreateEvent</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Resources required by this function could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The supplied <i>ObjectAttributes</i> structure contained an invalid parameter value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>EventType</i> parameter was invalid. The allowable <i>EventType</i> values are <b>NotificationEvent</b> or <b>SynchronizationEvent</b>. The REALTIME_OBJECT_FLAG can also be specified for these <i>EventType</i> parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> in the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the <b>OBJECT_ATTRIBUTES</b> structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required privilege to create a handle with the access specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
</table>
 




## -remarks



<b>ZwCreateEvent</b> creates an event object, sets it initial state to the specified value, and opens a handle to the object with the specified desired access. 

<b>ZwCreateEvent</b> can create either notification or synchronization events.

Events are used to coordinate execution. Events can be used by file system drivers to allow a caller to wait for completion of the requested operation until the given event is set to the Signaled state. 

Notification events can be used to notify one or more threads of execution that an event has occurred. Synchonization events can be used in the serialization of access to hardware between two otherwise unrelated drivers. 

A synchonization event is auto-resetting. When a synchronization event is set to the Signaled state, a single thread of execution that was waiting for the event to be signaled is released, and the event is automatically reset to the Not-Signaled state.

Unlike a synchronization event, a notification event is not auto-resetting. Once a notification event is in the Signaled state, it remains in that state until it is explicitly reset.

To synchronize on a notification event:

<ol>
<li>
Create the notification event with <b>ZwCreateEvent</b> with the <i>EventType</i> parameter set to <b>NotificationEvent</b>.

</li>
<li>
Wait for the event to be signaled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567120">ZwWaitForSingleObject</a> with the <i>EventHandle</i> returned by <b>ZwCreateEvent</b>. More than one thread of execution can wait for a given notification event to be signaled. To poll instead of stall, specify a <i>Timeout</i> of zero to <b>ZwWaitForSingleObject</b>.

</li>
<li>
Close the handle to the notification event with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> when access to the event is no longer needed.

</li>
</ol>
The <b>ZwCreateEvent</b> function is called after the <b>InitializeObjectAttributes</b> macro is used to set attributes in the <b>OBJECT_ATTRIBUTES</b> structure for the object. 

There are two alternate ways to specify the name of the object passed to <b>ZwCreateEvent</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>.

</li>
<li>
As pathname relative to the directory represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>.

</li>
</ol>
To release the event, a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> with the event handle.

For more information about events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/event-objects">Event Objects</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwCreateEvent</b> routine occurs in user mode, you should use the name "<b>NtCreateEvent</b>" instead of "<b>ZwCreateEvent</b>". </div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatenotificationevent">IoCreateNotificationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567092">ZwSetEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567120">ZwWaitForSingleObject</a>
 

 

