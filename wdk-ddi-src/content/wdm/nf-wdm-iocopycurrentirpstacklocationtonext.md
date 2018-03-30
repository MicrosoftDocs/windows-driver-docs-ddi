---
UID: NF:wdm.IoCopyCurrentIrpStackLocationToNext
title: IoCopyCurrentIrpStackLocationToNext function
author: windows-driver-content
description: The IoCopyCurrentIrpStackLocationToNext routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.
old-location: kernel\iocopycurrentirpstacklocationtonext.htm
old-project: kernel
ms.assetid: f1940737-4543-4e48-8a4a-90430b16890a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoCopyCurrentIrpStackLocationToNext, IoCopyCurrentIrpStackLocationToNext routine [Kernel-Mode Driver Architecture], k104_11dd3823-a387-4699-a4c4-db88f8961b37.xml, kernel.iocopycurrentirpstacklocationtonext, wdm/IoCopyCurrentIrpStackLocationToNext
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoCopyCurrentIrpStackLocationToNext
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCopyCurrentIrpStackLocationToNext function


## -description


The <b>IoCopyCurrentIrpStackLocationToNext</b> routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.


## -parameters




### -param Irp [in, out]

A pointer to the IRP.


## -returns



None




## -remarks



A driver calls <b>IoCopyCurrentIrpStackLocationToNext</b> to copy the IRP parameters from its stack location to the next-lower driver's stack location.

After calling this routine, a driver typically sets an I/O completion routine with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a> before passing the IRP to the next-lower driver with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>. Drivers that pass on their IRP parameters but do not set an I/O completion routine should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> instead of this routine.

If your driver calls <b>IoSkipCurrentIrpStackLocation</b>, be careful not to modify the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the <b>IO_STACK_LOCATION</b> structure's <b>Parameters</b> union, and should not call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>
 

 

