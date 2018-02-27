---
UID: NF:wdm.IoGetCurrentIrpStackLocation
title: IoGetCurrentIrpStackLocation function
author: windows-driver-content
description: The IoGetCurrentIrpStackLocation routine returns a pointer to the caller's I/O stack location in the specified IRP.
old-location: kernel\iogetcurrentirpstacklocation.htm
old-project: kernel
ms.assetid: 75144188-728b-4613-ac69-8cadf0f60233
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoGetCurrentIrpStackLocation, IoGetCurrentIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_f92e53c7-8a26-4cb0-859b-b0a7be4dce6a.xml, kernel.iogetcurrentirpstacklocation, wdm/IoGetCurrentIrpStackLocation
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
-	IoGetCurrentIrpStackLocation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetCurrentIrpStackLocation function


## -description


The <b>IoGetCurrentIrpStackLocation</b> routine returns a pointer to the caller's I/O stack location in the specified IRP.


## -syntax


````
PIO_STACK_LOCATION IoGetCurrentIrpStackLocation(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a>.


## -returns



<b>IoGetCurrentIrpStackLocation</b> returns a pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that contains the I/O stack location for the driver.




## -remarks



Every driver must call <b>IoGetCurrentIrpStackLocation</b> with each IRP it is sent in order to get any parameters for the current request. Unless a driver supplies a dispatch routine for each <b>IRP_MJ_<i>XXX</i></b> code that the driver handles, the driver also must check its I/O stack location in the IRP to determine what operation is being requested.

If a driver is passing the same parameters that it received to the next-lower driver, it should call <a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> instead of getting a pointer to the next-lower stack location and copying the parameters manually.




## -see-also

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\wdm\nf-wdm-iogetnextirpstacklocation.md">IoGetNextIrpStackLocation</a>



<a href="..\wdm\nf-wdm-iosetnextirpstacklocation.md">IoSetNextIrpStackLocation</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetCurrentIrpStackLocation routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

