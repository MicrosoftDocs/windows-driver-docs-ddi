---
UID: NF:wdm.IoStartPacket
title: IoStartPacket function
author: windows-driver-content
description: The IoStartPacket routine calls the driver's StartIo routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy.
old-location: kernel\iostartpacket.htm
old-project: kernel
ms.assetid: b1fa148e-73e2-437f-bd3a-e879bd457c76
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoStartPacket, IoStartPacket routine [Kernel-Mode Driver Architecture], k104_d27461b9-32fe-4d7b-853d-fd110fcdb644.xml, kernel.iostartpacket, wdm/IoStartPacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStartPacket
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoStartPacket function


## -description


The <b>IoStartPacket</b> routine calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy. 


## -parameters




### -param DeviceObject [in]

Pointer to the target device object for the IRP.


### -param Irp [in]

Pointer to the IRP to be processed.


### -param Key [in, optional]

Pointer to a value that determines where to insert the packet into the device queue. If this is zero, the packet is inserted at the tail of the device queue.


### -param CancelFunction [in, optional]

Specifies the entry point for a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routine.


## -returns



None




## -remarks



If the driver is already busy processing a request for the target device object, then the packet is queued in the device queue. Otherwise, this routine calls the driver's <i>StartIo</i> routine with the specified IRP.

If a non-NULL <i>CancelFunction</i> pointer is supplied, it is set in the IRP so the driver's <i>Cancel</i> routine is called if the IRP is canceled before its completion.

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartPacket</b>.

Callers of <b>IoStartPacket</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, this routine is called from a device driver's Dispatch routine at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549674">IoSetCancelRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550358">IoStartNextPacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550363">IoStartNextPacketByKey</a>
 

 

