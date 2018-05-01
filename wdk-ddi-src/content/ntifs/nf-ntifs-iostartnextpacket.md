---
UID: NF:ntifs.IoStartNextPacket
title: IoStartNextPacket function
author: windows-driver-content
description: The IoStartNextPacket routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's StartIo routine.
old-location: kernel\iostartnextpacket.htm
old-project: kernel
ms.assetid: f1197dfd-03d7-4ac2-8f11-60da413e32b2
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: IoStartNextPacket, IoStartNextPacket routine [Kernel-Mode Driver Architecture], k104_5a02a1fa-cf0e-43b0-a4e8-db1da8ad110c.xml, kernel.iostartnextpacket, wdm/IoStartNextPacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStartNextPacket
product: Windows
targetos: Windows
req.typenames: 
---

# IoStartNextPacket function


## -description


The <b>IoStartNextPacket</b> routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.


### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled. 


## -returns



None




## -remarks



If there are no IRPs currently in the device queue for the target <i>DeviceObject</i>, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable </i>is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. 

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacket</b>.

Drivers that call <b>IoStartNextPacket </b>from their <i>StartIo</i> routine should be aware of recursion issues. If a driver can call <b>IoStartNextPacket</b> on a large number of requests in succession from its <i>StartIo</i> routine (for example, when a device error occurs and the driver is clearing out it device queue), you should set the <i>DeferredStartIo</i> attribute for the device by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a> routine. This attribute ensures that the next packet will not be issued until the previous <i>StartIo</i> call returns.

Callers of <b>IoStartNextPacket</b> must be running at IRQL = DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550363">IoStartNextPacketByKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550370">IoStartPacket</a>
 

 

