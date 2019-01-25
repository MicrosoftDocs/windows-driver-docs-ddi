---
UID: NE:wdfio._WDF_IO_QUEUE_DISPATCH_TYPE
title: "_WDF_IO_QUEUE_DISPATCH_TYPE" (wdfio.h)
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object.
old-location: wdf\wdf_io_queue_dispatch_type.htm
tech.root: wdf
ms.assetid: 90f2f490-ee29-4e20-94b2-65a9bba3e831
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_dd3d1037-0355-4f02-b0ec-4bd988df33d2.xml, WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE enumeration, WdfIoQueueDispatchInvalid, WdfIoQueueDispatchManual, WdfIoQueueDispatchMax, WdfIoQueueDispatchParallel, WdfIoQueueDispatchSequential, _WDF_IO_QUEUE_DISPATCH_TYPE, kmdf.wdf_io_queue_dispatch_type, wdf.wdf_io_queue_dispatch_type, wdfio/WDF_IO_QUEUE_DISPATCH_TYPE, wdfio/WdfIoQueueDispatchInvalid, wdfio/WdfIoQueueDispatchManual, wdfio/WdfIoQueueDispatchMax, wdfio/WdfIoQueueDispatchParallel, wdfio/WdfIoQueueDispatchSequential
ms.topic: enum
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfio.h
api_name:
-	WDF_IO_QUEUE_DISPATCH_TYPE
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
---

# _WDF_IO_QUEUE_DISPATCH_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_DISPATCH_TYPE</b> enumeration type identifies the request dispatching methods that can be associated with a framework queue object. 


## -enum-fields




### -field WdfIoQueueDispatchInvalid

Reserved for internal use.


### -field WdfIoQueueDispatchSequential

The I/O queue's requests are presented to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handlers</a> one at a time. The framework does not deliver the next request until a driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the current request.


### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's request handlers as soon as the requests are available. 


### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must retrieve requests from the queue by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a>.


### -field WdfIoQueueDispatchMax

Reserved for internal use only.


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>.



