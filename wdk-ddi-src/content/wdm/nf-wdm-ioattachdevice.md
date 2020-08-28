---
UID: NF:wdm.IoAttachDevice
title: IoAttachDevice function (wdm.h)
description: The IoAttachDevice routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.
old-location: kernel\ioattachdevice.htm
tech.root: kernel
ms.assetid: 0227751d-739b-4e0c-84bd-9135f117ec9b
ms.date: 04/30/2018
keywords: ["IoAttachDevice function"]
ms.keywords: IoAttachDevice, IoAttachDevice routine [Kernel-Mode Driver Architecture], k104_a4f21237-9d2c-4336-9956-5e24da79f4b2.xml, kernel.ioattachdevice, wdm/IoAttachDevice
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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

# IoAttachDevice function


## -description

The <b>IoAttachDevice</b> routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.

## -parameters

### -param SourceDevice 

[in]
Pointer to the caller-created device object.

### -param TargetDevice 

[in]
Pointer to a buffer containing the name of the device object to which the specified <i>SourceDevice</i> is to be attached.

### -param AttachedDevice 

[out]
Pointer to caller-allocated storage for a pointer. On return, contains a pointer to the target device object if the attachment succeeds.

## -returns

<b>IoAttachDevice</b> can return one of the following NTSTATUS values:

## -remarks

<b>IoAttachDevice</b> establishes layering between drivers so that the same IRPs can be sent to each driver in the chain.

This routine is used by intermediate drivers during initialization. It allows such a driver to attach its own device object to another device in such a way that any requests being made to the original device are given first to the intermediate driver.

The caller can be layered only at the top of an existing chain of layered drivers. <b>IoAttachDevice</b> searches for the highest device object layered over <i>TargetDevice</i> and attaches to that object (that can be the <i>TargetDevice</i>). Therefore, this routine must not be called if a driver that must be higher-level has already layered itself over the target device.

Note that for file system drivers and drivers in the storage stack, <b>IoAttachDevice</b> opens the target device with FILE_READ_ATTRIBUTES and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetrelateddeviceobject">IoGetRelatedDeviceObject</a>. This does not cause a file system to be mounted. Thus, a successful call to <b>IoAttachDevice</b> returns the device object of the storage driver, not that of the file system driver.

This routine sets the <b>AlignmentRequirement</b> in <i>SourceDevice</i> to the value in the next-lower device object and sets the <b>StackSize</b> to the value in the next-lower object plus one.

<div class="alert"><b>Warning</b>  <i>AttachedDevice</i>
      must point to a global memory location, such as the driver's device extension. <b>IoAttachDevice</b> opens the file object for the target device, updates <i>AttachedDevice</i>, performs the attach, and then closes the file object. Thus, the source device receives the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> requests for the file object before <b>IoAttachDevice</b> returns. The driver must forward these requests to the target device, and <i>AttachedDevice</i> must be a memory location accessible to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchCleanup</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchClose</a> routines.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioattachdevicetodevicestacksafe">IoAttachDeviceToDeviceStackSafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodetachdevice">IoDetachDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetrelateddeviceobject">IoGetRelatedDeviceObject</a>

