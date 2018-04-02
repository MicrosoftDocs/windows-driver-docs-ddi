---
UID: NF:wdm.IoSetNextIrpStackLocation
title: IoSetNextIrpStackLocation function
author: windows-driver-content
description: The IoSetNextIrpStackLocation routine sets the IRP stack location in a driver-allocated IRP to that of the caller.
old-location: kernel\iosetnextirpstacklocation.htm
old-project: kernel
ms.assetid: 39a0b4d3-691f-45ca-a616-f3e123026776
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoSetNextIrpStackLocation, IoSetNextIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_34f06977-f176-4590-9d5a-adffebbdd9b9.xml, kernel.iosetnextirpstacklocation, wdm/IoSetNextIrpStackLocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoSetNextIrpStackLocation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetNextIrpStackLocation function


## -description


The <b>IoSetNextIrpStackLocation</b> routine sets the IRP stack location in a driver-allocated IRP to that of the caller.


## -parameters




### -param Irp [in, out]

Pointer to the IRP whose stack location is to be set. 


## -returns



None




## -remarks



In general, this routine is seldom used by drivers. It is primarily used by drivers that require their own stack location in an IRP that they have allocated, on their own, to send to another driver.

<b>IoSetNextIrpStackLocation</b> is generally not needed because either:

<ul>
<li>
The driver received the IRP it is passing from another, higher-level driver, and so it already owns a stack location,

</li>
<li>
Or, the driver allocated the IRP but does not need its own stack location because it can keep everything that it needs in a context block whose address can be passed to its <i>IoCompletion</i> routine.

</li>
</ul>
Care should be taken if this routine is called, especially when allocating the IRP with <b>IoAllocateIrp</b> or <b>IoMakeAssociatedIrp</b>. The writer of the allocating driver must remember that a caller-specific stack location is not included in the number of stack locations required by the lower-level drivers to which it sends IRPs with <b>IoCallDriver</b>. A driver must explicitly specify a stack location for itself in its call to <b>IoAllocateIrp</b> or <b>IoMakeAssociatedIrp</b> if it calls <b>IoSetNextIrpStackLocation</b> with the IRP returned by either routine.

A driver cannot call <b>IoSetNextIrpStackLocation</b> with any IRP it allocates by calling <b>IoBuildAsynchronousFsdRequest</b>, <b>IoBuildDeviceIoControlRequest</b>, or <b>IoBuildSynchronousFsdRequest</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
 

 

