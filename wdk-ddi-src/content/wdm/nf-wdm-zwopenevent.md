---
UID: NF:wdm.ZwOpenEvent
title: ZwOpenEvent function
author: windows-driver-content
description: The ZwOpenEvent routine opens a handle to an existing named event object with the specified desired access.
old-location: kernel\zwopenevent.htm
old-project: kernel
ms.assetid: 1facaf24-ed94-4516-b9d6-bdcd8ac4b9e9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ZwOpenEvent, NtOpenEvent, wdm/NtOpenEvent, ZwOpenEvent routine [Kernel-Mode Driver Architecture], k111_b2349294-0e16-43ef-95cb-eecd213374b6.xml, kernel.zwopenevent, ZwOpenEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwOpenEvent
-	NtOpenEvent
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwOpenEvent function


## -description


The <b>ZwOpenEvent</b> routine opens a handle to an existing named event object with the specified desired access.


## -syntax


````
NTSTATUS ZwOpenEvent(
  _Out_ PHANDLE            EventHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters




#### - EventHandle [out]

A pointer to a variable that will receive the event object handle. The handle includes bookkeeping information, such as a reference count and security context.


#### - DesiredAccess [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the desired types of access for the event object. The following table contains the event-specific ACCESS_MASK values.
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


#### - ObjectAttributes [in]

A pointer to the object attributes structure that the caller supplied to be used for the specified object. These attributes would include the <b>ObjectName</b> and the handle attributes, for example. This parameter is initialized by calling the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro. 


## -returns


<b>ZwOpenEvent</b> returns STATUS_SUCCESS or an appropriate error status. This routine might return one of the following error status codes: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>
</td>
<td width="60%">
Resources that this function requires could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> structure was not supplied or contained an invalid parameter value. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID </b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> in the <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD </b></dt>
</dl>
</td>
<td width="60%">
The object path contained incorrect syntax. For example, the <i>ObjectAttributes</i> parameter does not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the <b>OBJECT_ATTRIBUTES</b> structure is an empty string or does not start with an OBJECT_NAME_PATH_SEPARATOR character.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The path to the object was not found, indicating that it does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The object name was not found, indicating that the object does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD </b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required privilege to create a handle with the access specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
</table> 



## -remarks


<b>ZwOpenEvent</b> opens an existing named event object and creates a handle to the object with the specified desired access.

<b>ZwOpenEvent</b> can open either notification or synchronization events.

Events are used to coordinate execution. File system drivers can use events to enable a caller to wait for completion of the requested operation until the given event is set to the Signaled state.

Notification events can be used to notify one or more threads of execution that an event has occurred. Synchonization events can be used in the serialization of access to hardware between two otherwise unrelated drivers.
<div class="alert"><b>Note</b>  If the call to the <b>ZwOpenEvent</b> function occurs in user mode, you should use the name "<b>NtOpenEvent</b>" instead of "<b>ZwOpenEvent</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wdm\nf-wdm-iocreatenotificationevent.md">IoCreateNotificationEvent</a>

<a href="..\ntifs\nf-ntifs-zwcreateevent.md">ZwCreateEvent</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\ntifs\nf-ntifs-zwsetevent.md">ZwSetEvent</a>

<a href="..\ntifs\nf-ntifs-zwwaitforsingleobject.md">ZwWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a>

<a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\wdm\nf-wdm-iocreatesynchronizationevent.md">IoCreateSynchronizationEvent</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenEvent routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

