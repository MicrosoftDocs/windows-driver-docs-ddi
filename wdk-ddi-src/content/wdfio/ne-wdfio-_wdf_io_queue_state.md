---
UID: NE:wdfio._WDF_IO_QUEUE_STATE
title: _WDF_IO_QUEUE_STATE (wdfio.h)
description: The WDF_IO_QUEUE_STATE enumeration type identifies the status of a framework queue object. The enumerators are used as bit masks.
old-location: wdf\wdf_io_queue_state.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_STATE enumeration"]
ms.keywords: DFQueueObjectRef_210e9189-4d80-4c0f-930b-319af65697d2.xml, WDF_IO_QUEUE_STATE, WDF_IO_QUEUE_STATE enumeration, WdfIoQueueAcceptRequests, WdfIoQueueDispatchRequests, WdfIoQueueDriverNoRequests, WdfIoQueueNoRequests, WdfIoQueuePnpHeld, _WDF_IO_QUEUE_STATE, kmdf.wdf_io_queue_state, wdf.wdf_io_queue_state, wdfio/WDF_IO_QUEUE_STATE, wdfio/WdfIoQueueAcceptRequests, wdfio/WdfIoQueueDispatchRequests, wdfio/WdfIoQueueDriverNoRequests, wdfio/WdfIoQueueNoRequests, wdfio/WdfIoQueuePnpHeld
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
req.typenames: WDF_IO_QUEUE_STATE
f1_keywords:
 - _WDF_IO_QUEUE_STATE
 - wdfio/_WDF_IO_QUEUE_STATE
 - WDF_IO_QUEUE_STATE
 - wdfio/WDF_IO_QUEUE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfio.h
api_name:
 - WDF_IO_QUEUE_STATE
---

# _WDF_IO_QUEUE_STATE enumeration (wdfio.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_STATE</b> enumeration type identifies the status of a framework queue object. The enumerators are used as bit masks.

## -enum-fields

### -field WdfIoQueueAcceptRequests

If set, the I/O queue can accept new I/O requests from the I/O manager and requests that are forwarded by the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a> and <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a> (or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>) methods. 

If not set, the framework cancels requests from the I/O manager and <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a> and fails requests from <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a> (or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>) with STATUS_WDF_BUSY.

### -field WdfIoQueueDispatchRequests

If set, the framework delivers the queue's requests to the driver (unless the <b>WdfIoQueuePnpHeld</b> bit is also set). If not set, the driver cannot obtain requests from the queue.

### -field WdfIoQueueNoRequests

If set, the I/O queue is empty.

### -field WdfIoQueueDriverNoRequests

If set, all requests that have been delivered to the driver have been completed.

### -field WdfIoQueuePnpHeld

If set, the framework has stopped delivering requests to the driver because the underlying device is not in its working (D0) state.

## -remarks

The WDF_IO_QUEUE_STATE enumeration type is used as the return value for the <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> method.

The following functions are defined in <i>wdfio.h</i>:

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>
