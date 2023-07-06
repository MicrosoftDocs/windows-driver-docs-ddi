---
UID: NF:ntifs.IoStartNextPacket
title: IoStartNextPacket function (ntifs.h)
description: Learn more about the IoStartNextPacket routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoStartNextPacket function"]
ms.keywords: IoStartNextPacket, kernel.iostartnextpacket, wdm/IoStartNextPacket
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, SpinLockSafe, StartIoRecursion, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoStartNextPacket
 - ntifs/IoStartNextPacket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoStartNextPacket
---

# IoStartNextPacket function (ntifs.h)

## -description

The **IoStartNextPacket** routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's [**StartIo**](../wdm/nc-wdm-driver_startio.md) routine.

## -parameters

### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.

### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled.

## -remarks

If there are no IRPs currently in the device queue for the target **DeviceObject**, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called [**IoStartPacket**](nf-ntifs-iostartpacket.md), it should pass TRUE in this routine's **Cancelable** parameter. If **Cancelable** is TRUE, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP.

Drivers that do not have a **StartIo** routine cannot call **IoStartNextPacket**.

Drivers that call **IoStartNextPacket** from their **StartIo** routine should be aware of recursion issues. If a driver can call **IoStartNextPacket** on a large number of requests in succession from its **StartIo** routine (for example, when a device error occurs and the driver is clearing out it device queue), you should set the **DeferredStartIo** attribute for the device by using [**IoSetStartIoAttributes**](nf-ntifs-iosetstartioattributes.md) routine. This attribute ensures that the next packet will not be issued until the previous **StartIo** call returns.

Callers of **IoStartNextPacket** must be running at IRQL = DISPATCH_LEVEL. Usually, this routine is called from a device driver's [**DpcForIsr**](../wdm/nc-wdm-io_dpc_routine.md) or [**CustomDpc**](../wdm/nc-wdm-kdeferred_routine.md) routine, both of which are run at IRQL = DISPATCH_LEVEL.

## -see-also

[**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md)

[**IoSetStartIoAttributes**](nf-ntifs-iosetstartioattributes.md)

[**IoStartNextPacketByKey**](nf-ntifs-iostartnextpacketbykey.md)

[**IoStartPacket**](nf-ntifs-iostartpacket.md)
