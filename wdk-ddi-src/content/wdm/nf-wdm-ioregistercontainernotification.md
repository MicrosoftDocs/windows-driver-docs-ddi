---
UID: NF:wdm.IoRegisterContainerNotification
title: IoRegisterContainerNotification function (wdm.h)
description: The IoRegisterContainerNotification routine registers a kernel-mode driver to receive notifications about a specified class of events.
old-location: kernel\ioregistercontainernotification.htm
tech.root: kernel
ms.assetid: 5cfef8cc-b6b8-4b97-b8da-bf579e26f64d
ms.date: 04/30/2018
ms.keywords: IoRegisterContainerNotification, IoRegisterContainerNotification routine [Kernel-Mode Driver Architecture], k104_f99c2826-04ed-4aa6-9f19-6f97953eda31.xml, kernel.ioregistercontainernotification, wdm/IoRegisterContainerNotification
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRegisterContainerNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterContainerNotification function


## -description


The <b>IoRegisterContainerNotification</b> routine registers a kernel-mode driver to receive notifications about a specified class of events. 


## -parameters




### -param NotificationClass [in]

Specifies the class of events for which the caller (driver) requests notifications. Set this parameter to the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff550554">IO_CONTAINER_NOTIFICATION_CLASS</a> enumeration value:

<ul>
<li>
<b>IoSessionStateNotification</b>

</li>
</ul>
For more information, see the following Remarks section. 


### -param CallbackFunction [in]

A pointer to a callback function that is implemented by the caller (driver). The I/O manager calls this function to notify the caller when an event of the class indicated by <i>NotificationClass</i> occurs. For <i>NotificationClass</i> = <b>IoSessionStateNotification</b>, this parameter is a pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a> function. However, the caller should cast this function pointer to type PIO_CONTAINER_NOTIFICATION_FUNCTION to match the parameter type. For more information, see the following Remarks section.


### -param NotificationInformation [in, optional]

A pointer to a caller-allocated buffer that contains the notification information structure for an event of the class specified by <i>NotificationClass</i>. For <i>NotificationClass</i> = <b>IoSessionStateNotification</b>, <i>NotificationInformation</i> points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550643">IO_SESSION_STATE_NOTIFICATION</a> structure. The caller must fill out this structure before it calls <b>IoRegisterContainerNotification</b>. During this call, <b>IoRegisterContainerNotification</b> copies the data from this structure, and the I/O manager does not access the driver's copy of the structure after the call returns.


### -param NotificationInformationLength [in]

The size, in bytes, of the notification information structure contained in the buffer that is pointed to by <i>NotificationInformation</i>. For <i>NotificationClass</i> = <b>IoSessionStateNotification</b>, set this parameter to <b>sizeof</b>(<b>IO_SESSION_STATE_NOTIFICATION</b>).


### -param CallbackRegistration [out]

A pointer to a location into which this routine writes the address of a container notification registration object. This object is an opaque, system object in which the I/O manager stores information about the caller's container notification registration. When notifications are no longer required, the caller cancels the registration by passing this object pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550396">IoUnregisterContainerNotification</a> routine.


## -returns



<b>IoRegisterContainerNotification</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>NotificationClass</i> is not a valid <b>IO_CONTAINER_NOTIFICATION_CLASS</b> enumeration constant. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The information in the structure that is pointed to by <i>NotificationInformation</i> is incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>NotificationInformationLength</i> does not equal the size of the notification information structure that is required for use with the specified <i>NotificationClass</i> parameter value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALREADY_COMMITTED</b></dt>
</dl>
</td>
<td width="60%">
The driver is already registered to receive <i>NotificationClass</i> notifications of events that are associated with the specified I/O object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operating system has insufficient resources to create the requested registration.

</td>
</tr>
</table>
 




## -remarks



This routine can potentially support notifications of events in a variety of event classes. In Windows 7, this routine supports only <b>IoSessionStateNotification</b> notifications, which notify a kernel-mode driver of changes in the status of user sessions that the driver is interested in. For user-mode applications, the <a href="https://go.microsoft.com/fwlink/p/?linkid=155043">WTSRegisterSessionNotification</a> function fills a similar role.

The function pointer type for the <i>CallbackFunction</i> parameter is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  (*PIO_CONTAINER_NOTIFICATION_FUNCTION)(
    );</pre>
</td>
</tr>
</table></span></div>
The caller should cast the callback function pointer to this type to match the <i>CallbackFunction</i> parameter type. <b>IoRegisterContainerNotification</b> determines the actual type of the callback function pointer from the <i>NotificationClass</i> parameter. For <i>NotificationClass</i> = <b>IoSessionStateNotification</b>, <i>CallbackFunction</i> points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550554">IO_CONTAINER_NOTIFICATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550643">IO_SESSION_STATE_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550396">IoUnregisterContainerNotification</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=155043">WTSRegisterSessionNotification</a>
 

 

