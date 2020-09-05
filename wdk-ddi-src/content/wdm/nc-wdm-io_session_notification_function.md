---
UID: NC:wdm.IO_SESSION_NOTIFICATION_FUNCTION
title: IO_SESSION_NOTIFICATION_FUNCTION (wdm.h)
description: The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in.
old-location: kernel\io_session_notification_function.htm
tech.root: kernel
ms.assetid: ff7a5191-35d9-4927-9c23-7f5ad0cfd7ab
ms.date: 04/30/2018
keywords: ["IO_SESSION_NOTIFICATION_FUNCTION callback function"]
ms.keywords: DrvrRtns_b956c11f-2757-437b-b406-958fdced8f94.xml, IO_SESSION_NOTIFICATION_FUNCTION, IO_SESSION_NOTIFICATION_FUNCTION callback, IO_SESSION_NOTIFICATION_FUNCTION callback function [Kernel-Mode Driver Architecture], kernel.io_session_notification_function, wdm/IO_SESSION_NOTIFICATION_FUNCTION
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_SESSION_NOTIFICATION_FUNCTION
 - wdm/IO_SESSION_NOTIFICATION_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_SESSION_NOTIFICATION_FUNCTION
---

# IO_SESSION_NOTIFICATION_FUNCTION callback function


## -description

The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in.

## -parameters

### -param SessionObject 

[in]
Pointer to an opaque, system object that contains information about the user session. The driver can pass this pointer value to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcontainerinformation">IoGetContainerInformation</a> routine as the <i>ContainerObject</i> parameter value.

### -param IoObject 

[in]
Pointer to an I/O object owned by the driver. This parameter is the I/O object pointer that the driver supplied to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a> routine when the driver previously registered to receive notifications of session events. The <b>IoRegisterContainerNotification</b> routine's <i>NotificationInformation</i> parameter points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_state_notification">IO_SESSION_STATE_NOTIFICATION</a> structure whose <b>IoObject</b> member points to the I/O object.

### -param Event 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_session_event">IO_SESSION_EVENT</a> enumeration constant that indicates which session event caused the notification callback.

### -param Context 

[in]
The context value that the driver previously supplied to the <b>IoRegisterContainerNotification</b> routine when the driver registered to receive notifications of session events. In the <b>IoRegisterContainerNotification</b> call, the driver supplied a pointer to an <b>IO_SESSION_STATE_NOTIFICATION</b> structure whose <b>Context</b> member contains the context value.

### -param NotificationPayload 

[in]
Pointer to a payload buffer that contains an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_connect_info">IO_SESSION_CONNECT_INFO</a> structure.

### -param PayloadLength 

[in]
The size, in bytes, of the buffer pointed to by <i>NotificationPayload</i>. The buffer size never needs exceeds the constant value IO_SESSION_MAX_PAYLOAD_SIZE, which is defined in the Wdm.h header file.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in the Ntstatus.h header file.

## -remarks

A kernel-mode driver implements this routine. The I/O manager calls this routine to notify the driver of session events.

To receive notifications of session events, a driver calls the <b>IoRegisterContainerNotification</b> routine and sets this routine's <i>CallbackFunction</i> parameter to point to the driver's IO_SESSION_NOTIFICATION_FUNCTION routine. The I/O object that the driver passes to <b>IoRegisterContainerNotification</b> determines whether the driver will receive notifications of events in a particular user session or of events in all sessions. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_state_notification">IO_SESSION_STATE_NOTIFICATION</a>.


#### Examples

To define an I/O-session notification routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an I/O-session notification routine that is named <code>MyIoSessionNotification</code>, use the IO_SESSION_NOTIFICATION_FUNCTION type as shown in this code example:


```
IO_SESSION_NOTIFICATION_FUNCTION MyIoSessionNotification;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
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
  }
```

The IO_SESSION_NOTIFICATION_FUNCTION function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_SESSION_NOTIFICATION_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_connect_info">IO_SESSION_CONNECT_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_session_event">IO_SESSION_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_state_notification">IO_SESSION_STATE_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcontainerinformation">IoGetContainerInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a>

