---
UID: NC:wdm.DRIVER_DISPATCH
title: DRIVER_DISPATCH (wdm.h)
description: The callback routine services various IRPs. For a list of function codes, see Remarks.
old-location: kernel\dispatchcleanup.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["DRIVER_DISPATCH callback function"]
ms.keywords: DRIVER_DISPATCH, DispatchCleanup, DispatchClose, DispatchCreate, DispatchCreateClose, DispatchDeviceControl, DispatchFlushBuffers, DispatchInternalDeviceControl, DispatchPnP, DispatchPower, DispatchQueryInformation, DispatchRead, DispatchReadWrite, DispatchSetInformation, DispatchShutdown, DispatchSystemControl, DispatchWrite, DrvrRtns_157dfedc-63c2-4924-ad5c-04ff9f746a94.xml, MyDispatch, MyDispatch routine [Kernel-Mode Driver Architecture], kernel.dispatchcleanup, wdm/MyDispatch
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_DISPATCH
 - wdm/DRIVER_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_DISPATCH
---

# DRIVER_DISPATCH callback function

## -description

The callback routine services various IRPs. For a list of function codes, see Remarks.

## -parameters

### -param DeviceObject

[in, out] Caller-supplied pointer to a [DEVICE_OBJECT](./ns-wdm-_device_object.md) structure. This is the device object for the target device, previously created by the driver's [AddDevice](./nc-wdm-driver_add_device.md) routine.

### -param Irp

[in, out] Caller-supplied pointer to an [IRP](./ns-wdm-_irp.md) structure that describes the requested I/O operation.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.

## -remarks

Input parameters for all *Dispatch* routines are supplied in the [IRP](./ns-wdm-_irp.md) structure pointed to by *Irp*. Additional parameters are supplied in the driver's associated I/O stack location, which is described by the [IO_STACK_LOCATION](./ns-wdm-_io_stack_location.md) structure and can be obtained by calling [IoGetCurrentIrpStackLocation](./nf-wdm-iogetcurrentirpstacklocation.md).

Generally, all *Dispatch* routines execute in an arbitrary thread context at IRQL = PASSIVE_LEVEL, but there are exceptions. For more information, see [Dispatch Routines and IRQLs](/windows-hardware/drivers/kernel/dispatch-routines-and-irqls).

For more information about dispatch routines, see [Writing Dispatch Routines](/windows-hardware/drivers/kernel/writing-dispatch-routines). For more information about IRPs, see [Handling IRPs](/windows-hardware/drivers/kernel/handling-irps).

| IRP | About implementing the callback |
|--|--|
| [IRP_MJ_CLEANUP](/windows-hardware/drivers/ifs/irp-mj-cleanup) | A driver's *DispatchCleanup* routine should be named *Xxx*DispatchCleanup, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchCleanup* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_CLEANUP]. |
| [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) | A driver's *DispatchClose* routine should be named ***Xxx*DispatchClose**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchClose* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_CLOSE]. |
| [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) | A driver's *DispatchCreate* routine should be named *Xxx*DispatchCreate, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchCreate* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_CREATE]. |
| [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) or [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) | A driver can provide a single *DispatchCreateClose* routine instead of separate *DispatchCreate* and [DispatchClose]() routines.<br><br>A driver's *DispatchCreateClose* routine should be named ***Xxx*DispatchCreateClose**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchCreateClose* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_CREATE] and in *DriverObject*->**MajorFunction**[IRP_MJ_CLOSE]. |
| [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control) | A driver's *DispatchDeviceControl* routine should be named ***Xxx*DispatchDeviceControl**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchDeviceControl* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_DEVICE_CONTROL].<br><br>The system uses the FILE_*XXX* flags in the I/O control code to determine whether the IRP sender has the privileges to send the IRP to the device object. Drivers for Windows Server 2003 and later versions of Windows can use the [IoValidateDeviceIoControlAccess](./nf-wdm-iovalidatedeviceiocontrolaccess.md) routine to perform stricter access checks within *DispatchDeviceControl*. |
| [IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers) | A driver's *DispatchFlushBuffers* routine should be named *Xxx*DispatchFlushBuffers, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchFlushBuffers* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_FLUSH_BUFFERS]. |
| [IRP_MJ_INTERNAL_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-internal-device-control) | A driver's *DispatchInternalDeviceControl* routine should be named ***Xxx*DispatchInternalDeviceControl**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchInternalDeviceControl* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_INTERNAL_DEVICE_CONTROL]. |
| [IRP_MJ_PNP](/windows-hardware/drivers/ifs/irp-mj-pnp) | A driver's *DispatchPnP* routine should be named *Xxx*DispatchPnP, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchPnP* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_PNP]. |
| [IRP_MJ_POWER](/windows-hardware/drivers/kernel/irp-mj-power) | A driver's *DispatchPower* routine should be named ***Xxx*DispatchPower**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchPower* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_POWER]. |
| [IRP_MJ_QUERY_INFORMATION](/windows-hardware/drivers/ifs/irp-mj-query-information) | A driver's *DispatchQueryInformation* routine should be named ***Xxx*DispatchQueryInformation**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchQueryInformation* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_QUERY_INFORMATION]. |
| [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) | A driver's *DispatchRead* routine should be named ***Xxx*DispatchRead**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchRead* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_READ]. |
| [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read) or [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write) | A driver can provide a single *DispatchReadWrite* routine instead of separate [DispatchRead]() and [DispatchWrite]() routines.<br><br>A driver's *DispatchReadWrite* routine should be named ***Xxx*DispatchReadWrite**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchReadWrite* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_READ] and in *DriverObject*->**MajorFunction**[IRP_MJ_WRITE]. |
| [IRP_MJ_SET_INFORMATION](/windows-hardware/drivers/ifs/irp-mj-set-information) | A driver's *DispatchSetInformation* routine should be named ***Xxx*DispatchSetInformation**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchSetInformation* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_SET_INFORMATION]. |
| [IRP_MJ_SHUTDOWN](/windows-hardware/drivers/ifs/irp-mj-shutdown) | A driver's *DispatchShutdown* routine should be named ***Xxx*DispatchShutdown**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchShutdown* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_SHUTDOWN].<br><br>Additionally, in order to receive **IRP_MJ_SHUTDOWN** requests, a driver must call [IoRegisterShutdownNotification](./nf-wdm-ioregistershutdownnotification.md) or [IoRegisterLastChanceShutdownNotification](./nf-wdm-ioregisterlastchanceshutdownnotification.md) to register its *DispatchShutdown* routine with the system. |
| [IRP_MJ_SYSTEM_CONTROL](/windows-hardware/drivers/kernel/irp-mj-system-control) | A driver's *DispatchSystemControl* routine should be named ***Xxx*DispatchSystemControl**, where ***Xxx*** is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchSystemControl* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_SYSTEM_CONTROL]. |
| [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write) | A driver's *DispatchWrite* routine should be named ***Xxx*DispatchWrite**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *DispatchWrite* routine's address in *DriverObject*->**MajorFunction**[IRP_MJ_WRITE]. |

### Examples

To define a callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *DispatchCleanup* callback routine that is named `MyDispatchCleanup`, use the DRIVER_DISPATCH type as shown in this code example:

```cpp
DRIVER_DISPATCH MyDispatchCleanup;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
  MyDispatchCleanup(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }
```

The DRIVER_DISPATCH function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the_Use_decl_annotations_annotation to your function definition. The_Use_decl_annotations_annotation ensures that the annotations that are applied to the DRIVER_DISPATCH function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).