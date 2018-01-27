---
UID: NS:wdm._IO_SESSION_STATE_NOTIFICATION
title: _IO_SESSION_STATE_NOTIFICATION
author: windows-driver-content
description: The IO_SESSION_STATE_NOTIFICATION structure contains information that a kernel-mode driver supplies to the IoRegisterContainerNotification routine when the driver registers to receive notifications of session events.
old-location: kernel\io_session_state_notification.htm
old-project: kernel
ms.assetid: 19ff9c3a-d416-4468-b5a5-e2e6e896802a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PIO_SESSION_STATE_NOTIFICATION, PIO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_LOGON_EVENT, wdm/IO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_ALL_EVENTS, IO_SESSION_STATE_VALID_EVENT_MASK, kstruct_b_b25d50a3-6254-4eeb-800e-c5fc73c56dfb.xml, _IO_SESSION_STATE_NOTIFICATION, *PIO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_CREATION_EVENT, IO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_NOTIFICATION structure [Kernel-Mode Driver Architecture], IO_SESSION_STATE_TERMINATION_EVENT, IO_SESSION_STATE_DISCONNECT_EVENT, IO_SESSION_STATE_LOGOFF_EVENT, kernel.io_session_state_notification, PIO_SESSION_STATE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], IO_SESSION_STATE_CONNECT_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	IO_SESSION_STATE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: *PIO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_NOTIFICATION
req.product: Windows 10 or later.
---

# _IO_SESSION_STATE_NOTIFICATION structure


## -description


The <b>IO_SESSION_STATE_NOTIFICATION</b> structure contains information that a kernel-mode driver supplies to the <a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a> routine when the driver registers to receive notifications of session events.


## -syntax


````
typedef struct _IO_SESSION_STATE_NOTIFICATION {
  ULONG Size;
  ULONG Flags;
  PVOID IoObject;
  ULONG EventMask;
  PVOID Context;
} IO_SESSION_STATE_NOTIFICATION, *PIO_SESSION_STATE_NOTIFICATION;
````


## -struct-fields




### -field Size

The size, in bytes, of the <b>IO_SESSION_STATE_NOTIFICATION</b> structure.


### -field Flags

No flags are currently defined for this member. Set to zero. 


### -field IoObject

A pointer to an I/O object owned by the driver. This member can point to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>, <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>, or <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure. The I/O object must remain valid for the lifetime of the registration. Before you delete a registered device object, unload a registered driver, or close a registered file object, call the <a href="..\wdm\nf-wdm-iounregistercontainernotification.md">IoUnregisterContainerNotification</a> routine to cancel the registration. A driver can maintain simultaneous registrations for more than one I/O object, but it cannot create more than one active registration for the same I/O object. 


### -field EventMask

Mask bits for session events. These mask bits indicate the events for which the driver requests notifications.

To register to receive notifications of session events, a kernel-mode driver calls the <a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a> routine. To specify the session events for which the driver wants to receive notifications, the driver sets this structure's <b>EventMask</b> member to the bitwise OR of one or more <b>IO_SESSION_STATE_<i>XXX</i></b> constants. 

Set this member to the bitwise OR of one or more of the following <b>IO_SESSION_STATE_<i>XXX</i></b> constants:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_ALL_EVENTS"></a><a id="io_session_state_all_events"></a><dl>
<dt><b>IO_SESSION_STATE_ALL_EVENTS</b></dt>
<dt>0xffffffff</dt>
</dl>
</td>
<td width="60%">
Send notifications of all session events.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CREATION_EVENT"></a><a id="io_session_state_creation_event"></a><dl>
<dt><b>IO_SESSION_STATE_CREATION_EVENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is created.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_TERMINATION_EVENT"></a><a id="io_session_state_termination_event"></a><dl>
<dt><b>IO_SESSION_STATE_TERMINATION_EVENT</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session ends.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CONNECT_EVENT"></a><a id="io_session_state_connect_event"></a><dl>
<dt><b>IO_SESSION_STATE_CONNECT_EVENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is connected.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_DISCONNECT_EVENT"></a><a id="io_session_state_disconnect_event"></a><dl>
<dt><b>IO_SESSION_STATE_DISCONNECT_EVENT</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is disconnected.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGON_EVENT"></a><a id="io_session_state_logon_event"></a><dl>
<dt><b>IO_SESSION_STATE_LOGON_EVENT</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user logs on to the session.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGOFF_EVENT"></a><a id="io_session_state_logoff_event"></a><dl>
<dt><b>IO_SESSION_STATE_LOGOFF_EVENT</b></dt>
<dt>0x00000020</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user logs off of the session.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_VALID_EVENT_MASK"></a><a id="io_session_state_valid_event_mask"></a><dl>
<dt><b>IO_SESSION_STATE_VALID_EVENT_MASK</b></dt>
<dt>0x0000003f</dt>
</dl>
</td>
<td width="60%">
Send a notification when any type of session event occurs.

</td>
</tr>
</table> 


### -field Context

A pointer to a context buffer in which the driver can store its private data for a particular session notification registration. The I/O manager passes this pointer to the driver's notification callback routine (specified by the <b>IoRegisterContainerNotification</b> routine's <i>CallbackFunction</i> parameter). The I/O manager does not try to validate the <i>Context</i> pointer or to access the buffer that it points to. This member can be <b>NULL</b> if the driver does not require a context buffer. 


## -remarks


This structure is used by the <b>IoRegisterContainerNotification</b> routine. A driver that calls <b>IoRegisterContainerNotification</b> uses this structure to specify the session event notifications that it is registering for.

A per-session device object represents a device that can be accessed only by a particular user session. If a driver sets the <b>IoObject</b> member to point to a device object that is a per-session device object, <b>IoRegisterContainerNotification</b> registers the driver to receive only notifications of events that occur in the session that is represented by the device object. If <b>IoObject</b> points to a device object that is not a per-session device object, or if <b>IoObject</b> points to an object that is not a device object, <b>IoRegisterContainerNotification</b> registers the driver to receive notifications of events that occur in all sessions on the computer.

To determine whether a device object is a per-session device object, a driver can call the <a href="..\wdm\nf-wdm-iogetdevicepropertydata.md">IoGetDevicePropertyData</a> routine to query the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a> property key in the property store of the device object. If the <b>DEVPKEY_Device_SessionId</b> property exists and the value of the property is set to a nonzero <a href="http://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier, the device object is a per-session device object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a>. 



## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a>

<a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a>

<a href="..\wdm\nf-wdm-iogetdevicepropertydata.md">IoGetDevicePropertyData</a>

<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SESSION_STATE_NOTIFICATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

