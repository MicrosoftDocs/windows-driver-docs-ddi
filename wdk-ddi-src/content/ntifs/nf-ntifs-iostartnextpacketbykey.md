---
UID: NF:ntifs.IoStartNextPacketByKey
title: IoStartNextPacketByKey function (ntifs.h)
description: Learn more about the IoStartNextPacketByKey routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoStartNextPacketByKey function"]
ms.keywords: IoStartNextPacketByKey, kernel.iostartnextpacketbykey, wdm/IoStartNextPacketByKey
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoStartNextPacketByKey
 - ntifs/IoStartNextPacketByKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoStartNextPacketByKey
---

# IoStartNextPacketByKey function (ntifs.h)

## -description

The **IoStartNextPacketByKey** routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's [**StartIo**](../wdm/nc-wdm-driver_startio.md) routine with that IRP.

## -parameters

### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.

### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled.

### -param Key [in]

Specifies the sort key that determines which entry to remove from the queue.

## -remarks

If there are no IRPs currently in the device queue for the target device object, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called [**IoStartPacket**](nf-ntifs-iostartpacket.md), it should pass TRUE in this routine's **Cancelable** parameter. If **Cancelable** is TRUE, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP.

Drivers that do not have a **StartIo** routine cannot call **IoStartNextPacketByKey**.

Callers of **IoStartNextPacketByKey** must be running at IRQL <= DISPATCH_LEVEL. Usually, this routine is called from a device driver's [**DpcForIsr**](../wdm/nc-wdm-io_dpc_routine.md) or [**CustomDpc**](../wdm/nc-wdm-kdeferred_routine.md) routine, both of which are run at IRQL = DISPATCH_LEVEL.

## -see-also

[**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md)

[**IoStartNextPacket**](nf-ntifs-iostartnextpacket.md)

[**IoStartPacket**](nf-ntifs-iostartpacket.md)
