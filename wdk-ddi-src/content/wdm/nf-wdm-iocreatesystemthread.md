---
UID: NF:wdm.IoCreateSystemThread
title: IoCreateSystemThread function (wdm.h)
description: The IoCreateSystemThread routine creates a system thread that executes in kernel mode, and supplies a handle for the thread.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoCreateSystemThread function"]
ms.keywords: IoCreateSystemThread, IoCreateSystemThread routine [Kernel-Mode Driver Architecture], kernel.iocreatesystemthread, wdm/IoCreateSystemThread
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCreateSystemThread
 - wdm/IoCreateSystemThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateSystemThread
---

## -description

The **IoCreateSystemThread** routine creates a system thread that executes in kernel mode, and supplies a handle for the thread.

## -parameters

### -param IoObject [in, out]

A pointer to the [**DEVICE_OBJECT**](./ns-wdm-_device_object.md) or [**DRIVER_OBJECT**](./ns-wdm-_driver_object.md) to associate with          the created thread. **IoCreateSystemThread** takes a counted reference to this object. The I/O manager later releases this reference when the thread exits. For more information, see Remarks.

### -param ThreadHandle [out]

A pointer to a variable to which the routine writes the kernel handle for the created thread. When the handle is no longer needed, the driver must close the handle by calling the [ZwClose](../ntifs/nf-ntifs-ntclose.md) routine.

### -param DesiredAccess [in]

The [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) value that represents the types of access the caller requests to the created thread.

### -param ObjectAttributes [in, optional]

A pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the thread object's attributes. The OBJ_PERMANENT, OBJ_EXCLUSIVE, and OBJ_OPENIF attributes are not valid attributes for a thread object. If the caller is not running in the system process context, it must set the OBJ_KERNEL_HANDLE attribute in the **OBJECT_ATTRIBUTES** structure.

### -param ProcessHandle [in, optional]

An open handle for the process in whose address space the created thread is to run. The caller's thread must have PROCESS_CREATE_THREAD access to this process. If this parameter is **NULL**, the thread will be created in the initial system process. This parameter should be **NULL** for a driver-created thread. Use the **NtCurrentProcess** macro, defined in the Wdm.h header file, to specify the current process.

### -param ClientId [out, optional]

A pointer to a structure to which the routine writes the client identifier for the created thread. This parameter should be **NULL** for a driver-created thread.

### -param StartRoutine [in]

A pointer to a [ThreadStart](./nc-wdm-kstart_routine.md) routine that is the entry point for the created thread.

### -param StartContext [in, optional]

A context pointer that is passed as the *StartContext* parameter to the [ThreadStart](./nc-wdm-kstart_routine.md) routine when the created thread starts to run.

## -returns

**IoCreateSystemThread** returns STATUS_SUCCESS if the new thread was successfully created. Possible return values include the following error status codes.

| Return code | Description |
|---|---|
| **STATUS_INVALID_HANDLE** | *ProcessHandle* is not a valid process handle. |
| **STATUS_PROCESS_IS_TERMINATING** | The process specified by *ProcessHandle* is terminating. |
| **STATUS_INSUFFICIENT_RESOURCES** | Insufficient system resources are available to perform the requested operation. |

## -remarks

Starting with Windows 8, a driver can call **IoCreateSystemThread** to create a device-dedicated thread.
     This routine creates a new system thread that has no thread environment block (TEB) or user-mode context, and runs only in kernel mode.

Typically, the driver calls **IoCreateSystemThread** either when it starts the device, or when the driver's *Dispatch*Xxx routines start to receive I/O requests. For example, a driver might call this routine to create a thread when a *Dispatch*Xxx routine receives an asynchronous device control request.

If the *ProcessHandle* parameter is **NULL**, the created thread is associated with the system process. Such a thread continues running until either the system is shut down or the thread exits.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the *ObjectAttributes* parameter of **IoCreateSystemThread**. This attribute restricts the use of the handle returned by **IoCreateSystemThread** to processes running in kernel mode. Otherwise, the thread handle could be accessed by the process in whose context the driver is running. Drivers can call the [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) macro to set the OBJ_KERNEL_HANDLE attribute in the object attributes, as shown in the following code example.

```cpp
OBJECT_ATTRIBUTES ObjectAttributes;

InitializeObjectAttributes(&ObjectAttributes, NULL, OBJ_KERNEL_HANDLE, NULL, NULL);
```

**IoCreateSystemThread** is similar to the [PsCreateSystemThread](./nf-wdm-pscreatesystemthread.md) routine, but has an additional parameter, *IoObject*, which is a pointer to the caller's driver object or device object. **IoCreateSystemThread** uses this parameter to ensure that the driver cannot unload while the created thread exists. Before scheduling *StartRoutine* to run in this thread, **IoCreateSystemThread** takes a counted reference to the *IoObject* object. The I/O manager releases this reference after the created thread exits. Thus, this object persists for the lifetime of the created thread.

In contrast to a system thread that is created by the [PsCreateSystemThread](./nf-wdm-pscreatesystemthread.md) routine, a thread created by **IoCreateSystemThread** does not call the [PsTerminateSystemThread](./nf-wdm-psterminatesystemthread.md) routine to terminate itself. Instead, the I/O manager calls **PsTerminateSystemThread** on behalf of the created thread when the thread exits.

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[**DEVICE_OBJECT**](./ns-wdm-_device_object.md)

[**DRIVER_OBJECT**](./ns-wdm-_driver_object.md)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes)

[PsCreateSystemThread](./nf-wdm-pscreatesystemthread.md)

[PsTerminateSystemThread](./nf-wdm-psterminatesystemthread.md)

[ThreadStart](./nc-wdm-kstart_routine.md)

[ZwClose](../ntifs/nf-ntifs-ntclose.md)