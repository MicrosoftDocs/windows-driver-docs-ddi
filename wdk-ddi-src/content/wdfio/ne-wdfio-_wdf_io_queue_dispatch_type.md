---
UID: NE:wdfio._WDF_IO_QUEUE_DISPATCH_TYPE
title: _WDF_IO_QUEUE_DISPATCH_TYPE (wdfio.h)
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object.
old-location: wdf\wdf_io_queue_dispatch_type.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_DISPATCH_TYPE enumeration"]
ms.keywords: DFQueueObjectRef_dd3d1037-0355-4f02-b0ec-4bd988df33d2.xml, WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE enumeration, WdfIoQueueDispatchInvalid, WdfIoQueueDispatchManual, WdfIoQueueDispatchMax, WdfIoQueueDispatchParallel, WdfIoQueueDispatchSequential, _WDF_IO_QUEUE_DISPATCH_TYPE, kmdf.wdf_io_queue_dispatch_type, wdf.wdf_io_queue_dispatch_type, wdfio/WDF_IO_QUEUE_DISPATCH_TYPE, wdfio/WdfIoQueueDispatchInvalid, wdfio/WdfIoQueueDispatchManual, wdfio/WdfIoQueueDispatchMax, wdfio/WdfIoQueueDispatchParallel, wdfio/WdfIoQueueDispatchSequential
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
targetos: Windows
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
f1_keywords:
 - _WDF_IO_QUEUE_DISPATCH_TYPE
 - wdfio/_WDF_IO_QUEUE_DISPATCH_TYPE
 - WDF_IO_QUEUE_DISPATCH_TYPE
 - wdfio/WDF_IO_QUEUE_DISPATCH_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfio.h
api_name:
 - _WDF_IO_QUEUE_DISPATCH_TYPE
 - WDF_IO_QUEUE_DISPATCH_TYPE
---

# _WDF_IO_QUEUE_DISPATCH_TYPE enumeration (wdfio.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_DISPATCH_TYPE</b> enumeration type identifies the request dispatching methods that can be associated with a framework queue object.

## -enum-fields

### -field WdfIoQueueDispatchInvalid:0

Reserved for internal use.

### -field WdfIoQueueDispatchSequential

The I/O queue's requests are presented to the driver's <a href="/windows-hardware/drivers/wdf/request-handlers">request handlers</a> one at a time. The framework does not deliver the next request until a driver has called <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the current request.

### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's request handlers as soon as the requests are available.

### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must retrieve requests from the queue by calling <a href="/windows-hardware/drivers/devtest/kmdf-wdfioqueueretrievenextrequest">WdfIoQueueRetrieveNextRequest</a>.

### -field WdfIoQueueDispatchMax

Reserved for internal use only.

## -remarks

For more information, see <a href="/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>.

