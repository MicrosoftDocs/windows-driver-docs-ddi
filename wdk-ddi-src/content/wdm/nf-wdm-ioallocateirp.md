---
UID: NF:wdm.IoAllocateIrp
title: IoAllocateIrp function (wdm.h)
description: The IoAllocateIrp routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller.
old-location: kernel\ioallocateirp.htm
tech.root: kernel
ms.assetid: 40abbdf8-3712-4724-8aef-16c247780c86
ms.date: 04/30/2018
keywords: ["IoAllocateIrp function"]
ms.keywords: IoAllocateIrp, IoAllocateIrp routine [Kernel-Mode Driver Architecture], k104_326eb80d-9bc3-4a91-9f33-710f7975808a.xml, kernel.ioallocateirp, wdm/IoAllocateIrp
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: ForwardedAtBadIrqlAllocate, IoAllocateComplete, IoAllocateForward, IoAllocateFree, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoReuseIrp, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, HwStorPortProhibitedDDIs, IoFreeIrp, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAllocateIrp
 - wdm/IoAllocateIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAllocateIrp
---

# IoAllocateIrp function


## -description

The **IoAllocateIrp** routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller. See also [**IsAllocateIrpEx**](./nf-wdm-ioallocateirpex.md).

## -parameters

### -param StackSize 

[in]
Specifies the number of I/O stack locations to be allocated for the IRP. This value must be at least equal to the **StackSize** of the next-lower driver's device object, but can be one greater than this value. The calling driver need not allocate a stack location in the IRP for itself.

### -param ChargeQuota 

[in]
Setting this to **TRUE** causes the memory allocated for the IRP to be charged against the quota for the current process. Should be set to **FALSE** by intermediate drivers. This can be set to **TRUE** only by highest-level drivers that are called in the context of the thread that originates the I/O request for which the driver is allocating another IRP.

## -returns

**IoAllocateIrp** returns a pointer to an IRP, which was allocated from nonpaged system space, or **NULL** if an IRP could not be allocated.

## -remarks

The **IoAllocateIrp** routine does not associate the IRP with a thread. The allocating driver must free the IRP instead of completing it back to the I/O manager.

An intermediate or highest-level driver can call **IoAllocateIrp** to create IRPs for requests it sends to lower-level drivers. Such a driver must initialize the IRP and must set its [**IoCompletion**](./nc-wdm-io_completion_routine.md) routine in the IRP it creates so the caller can dispose of the IRP when lower-level drivers have completed processing of the request.

**IoAllocateIrp** automatically initializes the IRP's members. Do not use **IoInitializeIrp** to initialize the IRP before its first use. (You can use **IoInitializeIrp** to reuse an IRP that you have already used under certain special circumstances. See [Reusing IRPs](/windows-hardware/drivers/kernel/reusing-irps) for details.)

An intermediate or highest-level driver also can call [**IoBuildDeviceIoControlRequest**](./nf-wdm-iobuilddeviceiocontrolrequest.md), [**IoBuildAsynchronousFsdRequest**](./nf-wdm-iobuildasynchronousfsdrequest.md) or [**IoBuildSynchronousFsdRequest**](./nf-wdm-iobuildsynchronousfsdrequest.md) to set up requests it sends to lower-level drivers. Only a highest-level driver can call [**IoMakeAssociatedIrp**](../ntddk/nf-ntddk-iomakeassociatedirp.md).

## -see-also

[IO_STACK_LOCATION](./ns-wdm-_io_stack_location.md)

[IRP](./ns-wdm-_irp.md)

[**IoAllocateIrpEx**](./nf-wdm-ioallocateirpex.md)

[**IoBuildAsynchronousFsdRequest**](./nf-wdm-iobuildasynchronousfsdrequest.md)

[**IoBuildDeviceIoControlRequest**](./nf-wdm-iobuilddeviceiocontrolrequest.md)

[**IoBuildSynchronousFsdRequest**](./nf-wdm-iobuildsynchronousfsdrequest.md)

[**IoFreeIrp**](/windows-hardware/drivers/devtest/storport-iofreeirp)

[**IoMakeAssociatedIrp**](../ntddk/nf-ntddk-iomakeassociatedirp.md)

[**IoReuseIrp**](./nf-wdm-ioreuseirp.md)

[**IoSetCompletionRoutine**](./nf-wdm-iosetcompletionroutine.md)