---
UID: NF:wdm.IoBuildAsynchronousFsdRequest
title: IoBuildAsynchronousFsdRequest function (wdm.h)
description: The IoBuildAsynchronousFsdRequest routine allocates and sets up an IRP to be sent to lower-level drivers.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoBuildAsynchronousFsdRequest function"]
ms.keywords: IoBuildAsynchronousFsdRequest, IoBuildAsynchronousFsdRequest routine [Kernel-Mode Driver Architecture], k104_bbefd6f7-02b9-497d-9d9e-aef507436cd4.xml, kernel.iobuildasynchronousfsdrequest, wdm/IoBuildAsynchronousFsdRequest
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: ForwardedAtBadIrqlFsdAsync, IoBuildFsdComplete, IoBuildFsdForward, IoBuildFsdFree, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoBuildAsynchronousFsdRequest
 - wdm/IoBuildAsynchronousFsdRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoBuildAsynchronousFsdRequest
---

## -description

The **IoBuildAsynchronousFsdRequest** routine allocates and sets up an IRP to be sent to lower-level drivers.

## -parameters

### -param MajorFunction [in]

The major function code to be set in the IRP. This code can be [IRP_MJ_PNP](/windows-hardware/drivers/ifs/irp-mj-pnp), [IRP_MJ_READ](/windows-hardware/drivers/ifs/irp-mj-read), [IRP_MJ_WRITE](/windows-hardware/drivers/kernel/irp-mj-write), [IRP_MJ_FLUSH_BUFFERS](/windows-hardware/drivers/ifs/irp-mj-flush-buffers), or [IRP_MJ_SHUTDOWN](/windows-hardware/drivers/ifs/irp-mj-shutdown).

### -param DeviceObject [in]

A pointer to the next-lower driver's device object. This object represents the target device for the read, write, flush, or shutdown operation.

### -param Buffer [in, out]

A pointer to a buffer into which data is read or from which data is written. The value of this argument is **NULL** for flush and shutdown requests.

### -param Length [in, optional]

The length, in bytes, of the buffer pointed to by *Buffer*. For devices such as disks, this value must be an integer multiple of the sector size. Starting with Windows 8, the sector size can be 4,096 or 512 bytes. In earlier versions of Windows, the sector size is always 512 bytes. This parameter is required for read and write requests, but must be zero for flush and shutdown requests.

### -param StartingOffset [in, optional]

A pointer to the starting offset on the input/output media. The value of this argument is zero for flush and shutdown requests.

### -param IoStatusBlock [in, optional]

A pointer to the address of an I/O status block in which the to-be-called drivers return final status about the requested operation.

## -returns

**IoBuildAsynchronousFsdRequest** returns a pointer to an IRP, or a **NULL** pointer if the IRP cannot be allocated.

## -remarks

Intermediate or highest-level drivers can call **IoBuildAsynchronousFsdRequest** to set up IRPs for requests sent to lower-level drivers. The calling driver must supply an [IoCompletion](./nc-wdm-io_completion_routine.md) routine for the IRP, so the IRP can be deallocated with [IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp). For more information about IRP deallocation, see Examples.

The IRP that gets built contains only enough information to get the operation started and to complete the IRP. No other context information is tracked because an asynchronous request is context-independent.

Lower-level drivers might impose restrictions on parameters supplied to this routine. For example, disk drivers might require that values supplied for *Length* and *StartingOffset* be integer multiples of the device's sector size.

An intermediate or highest-level driver also can call [IoBuildDeviceIoControlRequest](./nf-wdm-iobuilddeviceiocontrolrequest.md), [IoAllocateIrp](./nf-wdm-ioallocateirp.md), or [IoBuildSynchronousFsdRequest](./nf-wdm-iobuildsynchronousfsdrequest.md) to set up requests it sends to lower-level drivers. Only a highest-level driver can call [IoMakeAssociatedIrp](../ntddk/nf-ntddk-iomakeassociatedirp.md).

During an **IoBuildAsynchronousFsdRequest** call, the I/O manager sets the **Tail.Overlay.Thread** member of the [IRP](./ns-wdm-_irp.md) structure to point to the caller's thread object, but does not take a counted reference to the thread object on behalf of the caller. After the caller sends the IRP to the driver for the target device, this driver might use the **Tail.Overlay.Thread** member to access the thread object. For example, a storage driver might call the [IoSetHardErrorOrVerifyDevice](../ntddk/nf-ntddk-iosetharderrororverifydevice.md) routine and supply a pointer to the IRP as an input parameter. During this call, **IoSetHardErrorOrVerifyDevice** uses the **Tail.Overlay.Thread** member to access the thread object. When the thread object is accessed in this way, the driver that called **IoBuildAsynchronousFsdRequest** to allocate the IRP is responsible for ensuring that the thread object stays valid while the IRP is being handled.

To keep the thread object valid, the driver that calls **IoBuildAsynchronousFsdRequest** can take a counted reference on the thread object before sending the IRP. For example, this driver can call the [ObReferenceObjectByPointerWithTag](./nf-wdm-obreferenceobjectbypointerwithtag.md) routine and supply, as the *Object* parameter, the object pointer from the **Tail.Overlay.Thread** member of the **IRP** structure. Later, this driver's completion routine can dereference the object by calling a routine such as [ObDereferenceObjectWithTag](./nf-wdm-obdereferenceobjectwithtag.md).

A driver might call **IoBuildAsynchronousFsdRequest** in one thread, and send the IRP allocated by this call in another thread. Before sending the IRP, this driver should set the **Tail.Overlay.Thread** member of the IRP to point to the thread object for the sending thread. Typically, the driver calls the [PsGetCurrentThread](../ntddk/nf-ntddk-psgetcurrentthread.md) routine to get the thread object pointer.

A driver that calls **IoBuildAsynchronousFsdRequest** to allocate an IRP does not necessarily need to take a counted reference on the thread object pointed to by the **Tail.Overlay.Thread** member of the IRP. The driver might instead use another technique to guarantee that this thread object remains valid while the IRP is being handled. For example, if the driver created the thread, the thread can wait until the IRP is completed to terminate itself.

### Examples

Before calling [IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp), an additional step is required to free the buffer for an IRP built by **IoBuildAsynchronousFsdRequest** if the following are all true:

- The buffer was allocated from system memory pool.

- In the device object for the target device, the DO_DIRECT_IO flag is set in the **DeviceObject->Flags** field.

- The **Irp->MdlAddress** field is non-NULL.

Before freeing the buffer for this IRP, call the [MmUnlockPages](./nf-wdm-mmunlockpages.md) routine with **Irp->MdlAddress** as the parameter value. This call decrements the extra reference count that **IoBuildAsynchronousFsdRequest** added to the pool pages in the MDL. Otherwise, the subsequent call to [IoFreeMdl](./nf-wdm-iofreemdl.md) will bug check because the reference count for these pool pages will be 2, not 1. The following code example shows the **MmUnlockPages**, **IoFreeMdl**, and **IoFreeIrp** calls for this case:

```cpp
if (((DeviceObject->Flags & DO_DIRECT_IO) == DO_DIRECT_IO) &&
    (Irp->MdlAddress != NULL))
{
    MmUnlockPages(Irp->MdlAddress);
}

IoFreeMdl(Irp->MdlAddress);
IoFreeIrp(Irp);
```

## -see-also

[IO_STACK_LOCATION](./ns-wdm-_io_stack_location.md)

[IRP](./ns-wdm-_irp.md)

[IoAllocateIrp](./nf-wdm-ioallocateirp.md)

[IoBuildDeviceIoControlRequest](./nf-wdm-iobuilddeviceiocontrolrequest.md)

[IoBuildSynchronousFsdRequest](./nf-wdm-iobuildsynchronousfsdrequest.md)

[IoCallDriver](./nf-wdm-iocalldriver.md)

[IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp)

[IoFreeMdl](./nf-wdm-iofreemdl.md)

[IoMakeAssociatedIrp](../ntddk/nf-ntddk-iomakeassociatedirp.md)

[IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md)

[IoSetHardErrorOrVerifyDevice](../ntddk/nf-ntddk-iosetharderrororverifydevice.md)

[MmUnlockPages](./nf-wdm-mmunlockpages.md)

[ObDereferenceObjectWithTag](./nf-wdm-obdereferenceobjectwithtag.md)

[ObReferenceObjectByPointerWithTag](./nf-wdm-obreferenceobjectbypointerwithtag.md)

[PsGetCurrentThread](../ntddk/nf-ntddk-psgetcurrentthread.md)