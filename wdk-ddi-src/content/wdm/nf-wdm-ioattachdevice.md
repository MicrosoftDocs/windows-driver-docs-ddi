---
UID: NF:wdm.IoAttachDevice
title: IoAttachDevice function (wdm.h)
description: The IoAttachDevice routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoAttachDevice function"]
ms.keywords: IoAttachDevice, IoAttachDevice routine [Kernel-Mode Driver Architecture], k104_a4f21237-9d2c-4336-9956-5e24da79f4b2.xml, kernel.ioattachdevice, wdm/IoAttachDevice
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive1, HwStorPortProhibitedDDIs
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
 - IoAttachDevice
 - wdm/IoAttachDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAttachDevice
---

## -description

The **IoAttachDevice** routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.

## -parameters

### -param SourceDevice [in]

Pointer to the caller-created device object.

### -param TargetDevice [in]

Pointer to a buffer containing the name of the device object to which the specified *SourceDevice* is to be attached.

### -param AttachedDevice [out]

Pointer to caller-allocated storage for a pointer. On return, contains a pointer to the target device object if the attachment succeeds.

## -returns

**IoAttachDevice** can return one of the following NTSTATUS values:

## -remarks

**IoAttachDevice** establishes layering between drivers so that the same IRPs can be sent to each driver in the chain.

This routine is used by intermediate drivers during initialization. It allows such a driver to attach its own device object to another device in such a way that any requests being made to the original device are given first to the intermediate driver.

The caller can be layered only at the top of an existing chain of layered drivers. **IoAttachDevice** searches for the highest device object layered over *TargetDevice* and attaches to that object (that can be the *TargetDevice*). Therefore, this routine must not be called if a driver that must be higher-level has already layered itself over the target device.

Note that for file system drivers and drivers in the storage stack, **IoAttachDevice** opens the target device with FILE_READ_ATTRIBUTES and then calls [IoGetRelatedDeviceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetrelateddeviceobject). This does not cause a file system to be mounted. Thus, a successful call to **IoAttachDevice** returns the device object of the storage driver, not that of the file system driver.

This routine sets the **AlignmentRequirement** in *SourceDevice* to the value in the next-lower device object and sets the **StackSize** to the value in the next-lower object plus one.

> [!WARNING]
> *AttachedDevice* must point to a global memory location, such as the driver's device extension. **IoAttachDevice** opens the file object for the target device, updates *AttachedDevice*, performs the attach, and then closes the file object. Thus, the source device receives the [IRP_MJ_CLEANUP](/windows-hardware/drivers/ifs/irp-mj-cleanup) and [IRP_MJ_CLOSE](/windows-hardware/drivers/kernel/irp-mj-close) requests for the file object before **IoAttachDevice** returns. The driver must forward these requests to the target device, and *AttachedDevice* must be a memory location accessible to the driver's [DispatchCleanup](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch) and [DispatchClose](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch) routines.

## -see-also

[DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[IoAttachDeviceToDeviceStack](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack)

[IoAttachDeviceToDeviceStackSafe](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioattachdevicetodevicestacksafe)

[IoCreateDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice)

[IoDetachDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iodetachdevice)

[IoGetRelatedDeviceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetrelateddeviceobject)
