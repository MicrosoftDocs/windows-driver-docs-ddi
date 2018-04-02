---
UID: NF:wdm.IoStartNextPacketByKey
title: IoStartNextPacketByKey function
author: windows-driver-content
description: The IoStartNextPacketByKey routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's StartIo routine with that IRP.
old-location: kernel\iostartnextpacketbykey.htm
old-project: kernel
ms.assetid: 25cf9026-fd5d-4998-b7ff-f7be048ef2a1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoStartNextPacketByKey, IoStartNextPacketByKey routine [Kernel-Mode Driver Architecture], k104_f2248acf-8071-43a6-b5f9-bc3bc178469b.xml, kernel.iostartnextpacketbykey, wdm/IoStartNextPacketByKey
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStartNextPacketByKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoStartNextPacketByKey function


## -description


The <b>IoStartNextPacketByKey</b> routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine with that IRP.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.


### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled.


### -param Key [in]

Specifies the sort key that determines which entry to remove from the queue.


## -returns



None




## -remarks



If there are no IRPs currently in the device queue for the target device object, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable</i>  is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. 

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacketByKey</b>.

Callers of <b>IoStartNextPacketByKey</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550358">IoStartNextPacket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550370">IoStartPacket</a>
 

 

