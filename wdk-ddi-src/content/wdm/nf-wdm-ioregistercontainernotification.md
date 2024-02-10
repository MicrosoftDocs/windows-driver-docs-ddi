---
UID: NF:wdm.IoRegisterContainerNotification
title: IoRegisterContainerNotification function (wdm.h)
description: The IoRegisterContainerNotification routine registers a kernel-mode driver to receive notifications about a specified class of events.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoRegisterContainerNotification function"]
ms.keywords: IoRegisterContainerNotification, IoRegisterContainerNotification routine [Kernel-Mode Driver Architecture], k104_f99c2826-04ed-4aa6-9f19-6f97953eda31.xml, kernel.ioregistercontainernotification, wdm/IoRegisterContainerNotification
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoRegisterContainerNotification
 - wdm/IoRegisterContainerNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoRegisterContainerNotification
---

## -description

The **IoRegisterContainerNotification** routine registers a kernel-mode driver to receive notifications about a specified class of events.

## -syntax

```cpp
NTSTATUS
IoRegisterContainerNotification(
    _In_ IO_CONTAINER_NOTIFICATION_CLASS NotificationClass,
    _In_ PIO_CONTAINER_NOTIFICATION_FUNCTION CallbackFunction,
    _In_reads_bytes_opt_(NotificationInformationLength) PVOID NotificationInformation,
    _In_ ULONG NotificationInformationLength,
    _Out_ PVOID * CallbackRegistration
    );```
## -parameters

### -param NotificationClass [in]

Specifies the class of events for which the caller (driver) requests notifications. Set this parameter to the following [IO_CONTAINER_NOTIFICATION_CLASS](./ne-wdm-_io_container_notification_class.md) enumeration value:

- **IoSessionStateNotification**

For more information, see the following Remarks section.

### -param CallbackFunction [in]

A pointer to a callback function that is implemented by the caller (driver). The I/O manager calls this function to notify the caller when an event of the class indicated by *NotificationClass* occurs. For *NotificationClass* = **IoSessionStateNotification**, this parameter is a pointer to a caller-supplied [IO_SESSION_NOTIFICATION_FUNCTION](./nc-wdm-io_session_notification_function.md) function. However, the caller should cast this function pointer to type PIO_CONTAINER_NOTIFICATION_FUNCTION to match the parameter type. For more information, see the following Remarks section.

### -param NotificationInformation [in, optional]

A pointer to a caller-allocated buffer that contains the notification information structure for an event of the class specified by *NotificationClass*. For *NotificationClass* = **IoSessionStateNotification**, *NotificationInformation* points to an [**IO_SESSION_STATE_NOTIFICATION**](./ns-wdm-_io_session_state_notification.md) structure. The caller must fill out this structure before it calls **IoRegisterContainerNotification**. During this call, **IoRegisterContainerNotification** copies the data from this structure, and the I/O manager does not access the driver's copy of the structure after the call returns.

### -param NotificationInformationLength [in]

The size, in bytes, of the notification information structure contained in the buffer that is pointed to by *NotificationInformation*. For *NotificationClass* = **IoSessionStateNotification**, set this parameter to **sizeof**(**IO_SESSION_STATE_NOTIFICATION**).

### -param CallbackRegistration [out]

A pointer to a location into which this routine writes the address of a container notification registration object. This object is an opaque, system object in which the I/O manager stores information about the caller's container notification registration. When notifications are no longer required, the caller cancels the registration by passing this object pointer to the [IoUnregisterContainerNotification](./nf-wdm-iounregistercontainernotification.md) routine.

## -returns

**IoRegisterContainerNotification** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER_1** | Parameter *NotificationClass* is not a valid **IO_CONTAINER_NOTIFICATION_CLASS** enumeration constant. |
| **STATUS_INVALID_PARAMETER_3** | The information in the structure that is pointed to by *NotificationInformation* is incorrect. |
| **STATUS_INVALID_PARAMETER_4** | Parameter *NotificationInformationLength* does not equal the size of the notification information structure that is required for use with the specified *NotificationClass* parameter value. |
| **STATUS_ALREADY_COMMITTED** | The driver is already registered to receive *NotificationClass* notifications of events that are associated with the specified I/O object. |
| **STATUS_INSUFFICIENT_RESOURCES** | The operating system has insufficient resources to create the requested registration. |

## -remarks

This routine can potentially support notifications of events in a variety of event classes. In Windows 7, this routine supports only **IoSessionStateNotification** notifications, which notify a kernel-mode driver of changes in the status of user sessions that the driver is interested in. For user-mode applications, the [WTSRegisterSessionNotification](/windows/win32/api/wtsapi32/nf-wtsapi32-wtsregistersessionnotification) function fills a similar role.

The function pointer type for the *CallbackFunction* parameter is defined as follows:

```cpp
typedef NTSTATUS
  (*PIO_CONTAINER_NOTIFICATION_FUNCTION)(
    );
```

The caller should cast the callback function pointer to this type to match the *CallbackFunction* parameter type. **IoRegisterContainerNotification** determines the actual type of the callback function pointer from the *NotificationClass* parameter. For *NotificationClass* = **IoSessionStateNotification**, *CallbackFunction* points to an [IO_SESSION_NOTIFICATION_FUNCTION](./nc-wdm-io_session_notification_function.md) function.

## -see-also

[IO_CONTAINER_NOTIFICATION_CLASS](./ne-wdm-_io_container_notification_class.md)

[IO_SESSION_NOTIFICATION_FUNCTION](./nc-wdm-io_session_notification_function.md)

[**IO_SESSION_STATE_NOTIFICATION**](./ns-wdm-_io_session_state_notification.md)

[IoUnregisterContainerNotification](./nf-wdm-iounregistercontainernotification.md)

[WTSRegisterSessionNotification](/windows/win32/api/wtsapi32/nf-wtsapi32-wtsregistersessionnotification)