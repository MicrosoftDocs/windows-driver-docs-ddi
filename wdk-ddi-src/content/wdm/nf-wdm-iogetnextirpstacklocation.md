---
UID: NF:wdm.IoGetNextIrpStackLocation
title: IoGetNextIrpStackLocation function
author: windows-driver-content
description: The IoGetNextIrpStackLocation routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver.
old-location: kernel\iogetnextirpstacklocation.htm
old-project: kernel
ms.assetid: 44d38686-7a66-4e27-9dc7-9b3b4dbdffd6
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoGetNextIrpStackLocation, IoGetNextIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_28da61f1-a732-4336-a14a-90a5bd2682c3.xml, kernel.iogetnextirpstacklocation, wdm/IoGetNextIrpStackLocation
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
-	IoGetNextIrpStackLocation
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetNextIrpStackLocation function


## -description


The <b>IoGetNextIrpStackLocation</b> routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver.


## -syntax


````
PIO_STACK_LOCATION IoGetNextIrpStackLocation(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the IRP. 


## -returns



<b>IoGetNextIrpStackLocation</b> returns a pointer to the next-lower-level driver's <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> in the given IRP.




## -remarks



Each driver that passes IRPs on to lower drivers must set up the stack location for the next lower driver. A driver calls <b>IoGetNextIrpStackLocation</b> to get a pointer to the next-lower driver's I/O stack location.

If a driver is passing the same parameters that it received to the next-lower driver, it should call <a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> instead of getting a pointer to the next-lower stack location and copying the parameters manually.

The return value is a pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551821">I/O Stack Locations</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>



<a href="..\wdm\nf-wdm-iosetnextirpstacklocation.md">IoSetNextIrpStackLocation</a>



<a href="..\wdm\nf-wdm-iogetcurrentirpstacklocation.md">IoGetCurrentIrpStackLocation</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetNextIrpStackLocation routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

