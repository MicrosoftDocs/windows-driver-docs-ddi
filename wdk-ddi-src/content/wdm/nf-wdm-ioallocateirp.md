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
f1_keywords:
 - "wdm/IoAllocateIrp"
 - "IoAllocateIrp"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoAllocateIrp
targetos: Windows
req.typenames: 
---

# IoAllocateIrp function

## -description

The **IoAllocateIrp** routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller. See also [**IsAllocateIrpEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirpex).

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

An intermediate or highest-level driver can call **IoAllocateIrp** to create IRPs for requests it sends to lower-level drivers. Such a driver must initialize the IRP and must set its [**IoCompletion**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine in the IRP it creates so the caller can dispose of the IRP when lower-level drivers have completed processing of the request.

**IoAllocateIrp** automatically initializes the IRP's members. Do not use **IoInitializeIrp** to initialize the IRP before its first use. (You can use **IoInitializeIrp** to reuse an IRP that you have already used under certain special circumstances. See [Reusing IRPs](https://docs.microsoft.com/windows-hardware/drivers/kernel/reusing-irps) for details.)

An intermediate or highest-level driver also can call [**IoBuildDeviceIoControlRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest), [**IoBuildAsynchronousFsdRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest) or [**IoBuildSynchronousFsdRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest) to set up requests it sends to lower-level drivers. Only a highest-level driver can call [**IoMakeAssociatedIrp**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iomakeassociatedirp).

## -see-also

[IO_STACK_LOCATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location)

[IRP](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp)

[**IoAllocateIrpEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirpex)

[**IoBuildAsynchronousFsdRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest)

[**IoBuildDeviceIoControlRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest)

[**IoBuildSynchronousFsdRequest**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest)

[**IoFreeIrp**](https://docs.microsoft.com/windows-hardware/drivers/devtest/storport-iofreeirp)

[**IoMakeAssociatedIrp**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iomakeassociatedirp)

[**IoReuseIrp**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreuseirp)

[**IoSetCompletionRoutine**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine)
