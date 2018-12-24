---
UID: NF:wdm.IoGetCurrentIrpStackLocation
title: IoGetCurrentIrpStackLocation function
description: The IoGetCurrentIrpStackLocation routine returns a pointer to the caller's I/O stack location in the specified IRP.
old-location: kernel\iogetcurrentirpstacklocation.htm
tech.root: kernel
ms.assetid: 75144188-728b-4613-ac69-8cadf0f60233
ms.date: 04/30/2018
ms.keywords: IoGetCurrentIrpStackLocation, IoGetCurrentIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_f92e53c7-8a26-4cb0-859b-b0a7be4dce6a.xml, kernel.iogetcurrentirpstacklocation, wdm/IoGetCurrentIrpStackLocation
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
-	IoGetCurrentIrpStackLocation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetCurrentIrpStackLocation function


## -description


The <b>IoGetCurrentIrpStackLocation</b> routine returns a pointer to the caller's I/O stack location in the specified IRP.


## -parameters




### -param Irp [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>.


## -returns



<b>IoGetCurrentIrpStackLocation</b> returns a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure that contains the I/O stack location for the driver.




## -remarks



Every driver must call <b>IoGetCurrentIrpStackLocation</b> with each IRP it is sent in order to get any parameters for the current request. Unless a driver supplies a dispatch routine for each <b>IRP_MJ_<i>XXX</i></b> code that the driver handles, the driver also must check its I/O stack location in the IRP to determine what operation is being requested.

If a driver is passing the same parameters that it received to the next-lower driver, it should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> instead of getting a pointer to the next-lower stack location and copying the parameters manually.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550321">IoSetNextIrpStackLocation</a>
 

 

