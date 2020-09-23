---
UID: NF:wdm.IoStartPacket
title: IoStartPacket function (wdm.h)
description: The IoStartPacket routine calls the driver's StartIo routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.
old-location: kernel\iostartpacket.htm
tech.root: kernel
ms.assetid: b1fa148e-73e2-437f-bd3a-e879bd457c76
ms.date: 04/30/2018
keywords: ["IoStartPacket function"]
ms.keywords: IoStartPacket, IoStartPacket routine [Kernel-Mode Driver Architecture], k104_d27461b9-32fe-4d7b-853d-fd110fcdb644.xml, kernel.iostartpacket, wdm/IoStartPacket
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
 - wdm/IoStartPacket
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

# IoStartPacket function (wdm.h)


## -description

The <b>IoStartPacket</b> routine calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a> routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.

## -parameters

### -param DeviceObject 

[in]
Pointer to the target device object for the IRP.

### -param Irp 

[in]
Pointer to the IRP to be processed.

### -param Key 

[in, optional]
Pointer to a value that determines where to insert the packet into the device queue. If this is zero, the packet is inserted at the tail of the device queue.

### -param CancelFunction 

[in, optional]
Specifies the entry point for a driver-supplied <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensionrequest-cancel">Cancel</a> routine.

## -remarks

If the driver is already busy processing a request for the target device object, then the packet is queued in the device queue. Otherwise, this routine calls the driver's <i>StartIo</i> routine with the specified IRP.

If a non-NULL <i>CancelFunction</i> pointer is supplied, it is set in the IRP so the driver's <i>Cancel</i> routine is called if the IRP is canceled before its completion.

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartPacket</b>.

Callers of <b>IoStartPacket</b> must be running at IRQL <= DISPATCH_LEVEL. Usually, this routine is called from a device driver's Dispatch routine at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcancelroutine">IoSetCancelRoutine</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacket">IoStartNextPacket</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacketbykey">IoStartNextPacketByKey</a>