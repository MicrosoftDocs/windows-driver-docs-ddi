---
UID: NF:wdm.IoAllocateIrpEx
title: IoAllocateIrpEx function (wdm.h)
description: IoAllocateIrpEx allocates an I/O request packet (IRP) from
tech.root: kernel
ms.date: 10/11/2019
keywords: ["IoAllocateIrpEx function"]
ms.keywords: IoAllocateIrpEx
req.header: wdm.h
req.include-header: wdm.h, ntddk.h, ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting Windows 10 (version 1507)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: ntoskrnl.lib
req.dll: ntoskrnl.exe
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntoskrnl.exe
api_name:
 - IoAllocateIrpEx
f1_keywords:
 - IoAllocateIrpEx
 - wdm/IoAllocateIrpEx
---

# IoAllocateIrpEx function


## -description

**IoAllocateIrpEx** allocates an IRP from the system nonpaged pool, possibly with an IRP extension.

## -parameters

### -param DeviceObject

Pointer to the device object to check to determine whether to add space for an IRP extension. When **DeviceObject** is set to DEVICE_WITH_IRP_EXTENSION, space for the IRP extension is also allocated.

### -param StackSize

Maximum number of stack locations to be allocated for the IRP. **StackSize** must be at least equal to the **StackSize** of the next-lower driver's device object, but can be one greater than this value. The calling driver does not need to allocate a stack location in the IRP for itself.

### -param ChargeQuota

Setting **ChargeQuota** to **TRUE** causes the memory allocated for the IRP to be charged against the quota for the current process. This parameter can be set **TRUE** only by the highest-level drivers that are called in the context of the thread that originates the I/O request for which the driver is allocating another IRP. Intermediate drivers should set this parameter to **FALSE**.

## -returns

**IoAllocateIrpEx** returns a pointer to the allocated and initialized IRP, or **NULL** if an IRP could not be allocated.

## -remarks

**IoAllocateIrpEx** allocates **StackSize** stack locations and initializes the IRP. It does not associate the IRP with a thread. The allocating driver must free the IRP instead of completing it back to the I/O manager.

An intermediate or highest-level driver can call **IoAllocateIrpEx** to create IRPs for requests it sends to lower-level drivers. Such a driver must initialize the IRP and must set its [*IoCompletion*](./nc-wdm-io_completion_routine.md) callback routine in the IRP it creates so the caller can dispose of the IRP when lower-level drivers have completed processing of the request.
IoAllocateIrp automatically initializes the IRP's members. Do not use IoInitializeIrp to initialize the IRP before its first use. (You can use IoInitializeIrp to reuse an IRP that you have already used under certain special circumstances. See [Reusing IRPs](/windows-hardware/drivers/kernel/reusing-irps) for details.)
An intermediate or highest-level driver also can call [**IoBuildDeviceIoControlRequest**](./nf-wdm-iobuilddeviceiocontrolrequest.md), [**IoBuildAsynchronousFsdRequest**](./nf-wdm-iobuildasynchronousfsdrequest.md) or [**IoBuildSynchronousFsdRequest**](./nf-wdm-iobuildsynchronousfsdrequest.md) to set up requests it sends to lower-level drivers. Only a highest-level driver can call [**IoMakeAssociatedIrp**](../ntddk/nf-ntddk-iomakeassociatedirp.md).

## -see-also

[IO_STACK_LOCATION](./ns-wdm-_io_stack_location.md)

[IRP](./ns-wdm-_irp.md)

[**IoAllocateIrp**](./nf-wdm-ioallocateirp.md)

[**IoBuildAsynchronousFsdRequest**](./nf-wdm-iobuildasynchronousfsdrequest.md)

[**IoBuildDeviceIoControlRequest**](./nf-wdm-iobuilddeviceiocontrolrequest.md)

[*IoCompletion*](./nc-wdm-io_completion_routine.md)

[**IoBuildSynchronousFsdRequest**](./nf-wdm-iobuildsynchronousfsdrequest.md)

[**IoFreeIrp**](/windows-hardware/drivers/devtest/storport-iofreeirp)

[**IoMakeAssociatedIrp**](../ntddk/nf-ntddk-iomakeassociatedirp.md)

[**IoReuseIrp**](./nf-wdm-ioreuseirp.md)

[**IoSetCompletionRoutine**](./nf-wdm-iosetcompletionroutine.md)
