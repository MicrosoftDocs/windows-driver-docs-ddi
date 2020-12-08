---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_READ
title: EVT_WDF_IO_QUEUE_IO_READ (wdfio.h)
description: A driver's EvtIoRead event callback function processes a specified read request.
old-location: wdf\evtioread.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_QUEUE_IO_READ callback function"]
ms.keywords: DFQueueObjectRef_d5f59efc-e7db-4c3e-9845-5ba0c4949cd5.xml, EVT_WDF_IO_QUEUE_IO_READ, EVT_WDF_IO_QUEUE_IO_READ callback, EvtIoRead, EvtIoRead callback function, kmdf.evtioread, wdf.evtioread, wdfio/EvtIoRead
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_IO_QUEUE_IO_READ
 - wdfio/EVT_WDF_IO_QUEUE_IO_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfio.h
api_name:
 - EvtIoRead
---

# EVT_WDF_IO_QUEUE_IO_READ callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoRead</i> event callback function processes a specified read request.

## -parameters

### -param Queue 

[in]
A handle to the framework queue object that is associated with the I/O request.

### -param Request 

[in]
A handle to a framework request object.

### -param Length 

[in]
The number of bytes to be read.

## -remarks

A driver registers an <i>EvtIoRead</i> callback function when it calls <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see  <a href="/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoRead</i> callback function for a device's I/O queue, the callback function receives every read request from the queue. For more information, see <a href="/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoRead</i> callback function must process each received I/O request in some manner. For more information, see <a href="/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Read requests require an output buffer, which receives data that the driver provides. For information about how the driver can access a read request's buffer, see <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoRead</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrainsynchronously">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestopsynchronously">WdfIoQueueStopSynchronously</a>
</dd>
</dl>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>



<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
