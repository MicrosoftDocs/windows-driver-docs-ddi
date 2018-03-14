---
UID: NC:wdm.IO_SESSION_NOTIFICATION_FUNCTION
title: IO_SESSION_NOTIFICATION_FUNCTION
author: windows-driver-content
description: The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in.
old-location: kernel\io_session_notification_function.htm
old-project: kernel
ms.assetid: ff7a5191-35d9-4927-9c23-7f5ad0cfd7ab
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: DrvrRtns_b956c11f-2757-437b-b406-958fdced8f94.xml, IO_SESSION_NOTIFICATION_FUNCTION, IO_SESSION_NOTIFICATION_FUNCTION callback function [Kernel-Mode Driver Architecture], kernel.io_session_notification_function, wdm/IO_SESSION_NOTIFICATION_FUNCTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.irql: Called at IRQL <= APC_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	IO_SESSION_NOTIFICATION_FUNCTION
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# IO_SESSION_NOTIFICATION_FUNCTION callback


## -description


The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in.


## -prototype


````
NTSTATUS IO_SESSION_NOTIFICATION_FUNCTION(
  _In_ PVOID SessionObject,
  _In_ PVOID IoObject,
  _In_ ULONG Event,
  _In_ PVOID Context,
  _In_ PVOID NotificationPayload,
  _In_ ULONG PayloadLength
);
````


## -parameters




### -param SessionObject [in]

Pointer to an opaque, system object that contains information about the user session. The driver can pass this pointer value to the <a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a> routine as the <i>ContainerObject</i> parameter value.


### -param IoObject [in]

Pointer to an I/O object owned by the driver. This parameter is the I/O object pointer that the driver supplied to the <a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a> routine when the driver previously registered to receive notifications of session events. The <b>IoRegisterContainerNotification</b> routine's <i>NotificationInformation</i> parameter points to an <a href="..\wdm\ns-wdm-_io_session_state_notification.md">IO_SESSION_STATE_NOTIFICATION</a> structure whose <b>IoObject</b> member points to the I/O object.


### -param Event [in]

An <a href="..\wdm\ne-wdm-_io_session_event.md">IO_SESSION_EVENT</a> enumeration constant that indicates which session event caused the notification callback.


### -param Context [in]

The context value that the driver previously supplied to the <b>IoRegisterContainerNotification</b> routine when the driver registered to receive notifications of session events. In the <b>IoRegisterContainerNotification</b> call, the driver supplied a pointer to an <b>IO_SESSION_STATE_NOTIFICATION</b> structure whose <b>Context</b> member contains the context value.


### -param NotificationPayload [in]

Pointer to a payload buffer that contains an <a href="..\wdm\ns-wdm-_io_session_connect_info.md">IO_SESSION_CONNECT_INFO</a> structure.


### -param PayloadLength [in]

The size, in bytes, of the buffer pointed to by <i>NotificationPayload</i>. The buffer size never needs exceeds the constant value IO_SESSION_MAX_PAYLOAD_SIZE, which is defined in the Wdm.h header file.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in the Ntstatus.h header file.




## -remarks



A kernel-mode driver implements this routine. The I/O manager calls this routine to notify the driver of session events.

To receive notifications of session events, a driver calls the <b>IoRegisterContainerNotification</b> routine and sets this routine's <i>CallbackFunction</i> parameter to point to the driver's IO_SESSION_NOTIFICATION_FUNCTION routine. The I/O object that the driver passes to <b>IoRegisterContainerNotification</b> determines whether the driver will receive notifications of events in a particular user session or of events in all sessions. For more information, see <a href="..\wdm\ns-wdm-_io_session_state_notification.md">IO_SESSION_STATE_NOTIFICATION</a>.


#### Examples

To define an an I/O-session notification routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an an I/O-session notification routine that is named <code>MyIoSessionNotification</code>, use the IO_SESSION_NOTIFICATION_FUNCTION type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_SESSION_NOTIFICATION_FUNCTION MyIoSessionNotification;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyIoSessionNotification(
    PVOID  SessionObject,
    PVOID  IoObject,
    ULONG  Event,
    PVOID  Context,
    PVOID  NotificationPayload,
    ULONG  PayloadLength
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_SESSION_NOTIFICATION_FUNCTION function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_SESSION_NOTIFICATION_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\ns-wdm-_io_session_state_notification.md">IO_SESSION_STATE_NOTIFICATION</a>



<a href="..\wdm\ne-wdm-_io_session_event.md">IO_SESSION_EVENT</a>



<a href="..\wdm\nf-wdm-iogetcontainerinformation.md">IoGetContainerInformation</a>



<a href="..\wdm\nf-wdm-ioregistercontainernotification.md">IoRegisterContainerNotification</a>



<a href="..\wdm\ns-wdm-_io_session_connect_info.md">IO_SESSION_CONNECT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SESSION_NOTIFICATION_FUNCTION callback function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

