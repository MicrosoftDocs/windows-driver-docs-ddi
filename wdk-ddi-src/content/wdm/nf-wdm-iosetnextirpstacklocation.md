---
UID: NF:wdm.IoSetNextIrpStackLocation
title: IoSetNextIrpStackLocation function
author: windows-driver-content
description: The IoSetNextIrpStackLocation routine sets the IRP stack location in a driver-allocated IRP to that of the caller.
old-location: kernel\iosetnextirpstacklocation.htm
old-project: kernel
ms.assetid: 39a0b4d3-691f-45ca-a616-f3e123026776
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k104_34f06977-f176-4590-9d5a-adffebbdd9b9.xml, IoSetNextIrpStackLocation, kernel.iosetnextirpstacklocation, IoSetNextIrpStackLocation routine [Kernel-Mode Driver Architecture], wdm/IoSetNextIrpStackLocation
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoSetNextIrpStackLocation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSetNextIrpStackLocation function


## -description


The <b>IoSetNextIrpStackLocation</b> routine sets the IRP stack location in a driver-allocated IRP to that of the caller.


## -syntax


````
VOID IoSetNextIrpStackLocation(
  _Inout_ PIRP Irp
);
````


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

<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>



<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>



<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetNextIrpStackLocation routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

