---
UID: NF:ntifs.IoStartPacket
title: IoStartPacket function (ntifs.h)
description: Learn more about the IoStartPacket routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoStartPacket function"]
ms.keywords: IoStartPacket, kernel.iostartpacket, wdm/IoStartPacket
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoStartPacket
 - ntifs/IoStartPacket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoStartPacket
---

# IoStartPacket function (ntifs.h)

## -description

The **IoStartPacket** routine calls the driver's [**StartIo**](../wdm/nc-wdm-driver_startio.md) routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.

## -parameters

### -param DeviceObject [in]

Pointer to the target device object for the IRP.

### -param Irp [in]

Pointer to the IRP to be processed.

### -param Key [in, optional]

Pointer to a value that determines where to insert the packet into the device queue. If this is zero, the packet is inserted at the tail of the device queue.

### -param CancelFunction [in, optional]

Specifies the entry point for a driver-supplied [**Cancel**](../wdm/nc-wdm-driver_cancel.md) routine.

## -remarks

If the driver is already busy processing a request for the target device object, then the packet is queued in the device queue. Otherwise, this routine calls the driver's **StartIo** routine with the specified IRP.

If a non-NULL **CancelFunction** pointer is supplied, it is set in the IRP so the driver's **Cancel** routine is called if the IRP is canceled before its completion.

Drivers that do not have a **StartIo** routine cannot call **IoStartPacket**.

Callers of **IoStartPacket** must be running at IRQL <= DISPATCH_LEVEL. Usually, this routine is called from a device driver's Dispatch routine at IRQL = PASSIVE_LEVEL.

## -see-also

[**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md)

[**IoMarkIrpPending**](../wdm/nf-wdm-iomarkirppending.md)

[**IoSetCancelRoutine**](../wdm/nf-wdm-iosetcancelroutine.md)

[**IoStartNextPacket**](nf-ntifs-iostartnextpacket.md)

[**IoStartNextPacketByKey**](nf-ntifs-iostartnextpacketbykey.md)
