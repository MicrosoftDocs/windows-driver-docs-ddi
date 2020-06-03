---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_DEFAULT
title: EVT_WDF_IO_QUEUE_IO_DEFAULT (wdfio.h)
description: A driver's EvtIoDefault event callback function processes a specified I/O request.
old-location: wdf\evtiodefault.htm
tech.root: wdf
ms.assetid: 0b834d01-5603-43e8-9b74-9292610cc06d
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_QUEUE_IO_DEFAULT callback function"]
ms.keywords: DFQueueObjectRef_aca0c34e-8d7d-4eba-b1ac-c91928db896e.xml, EVT_WDF_IO_QUEUE_IO_DEFAULT, EVT_WDF_IO_QUEUE_IO_DEFAULT callback, EvtIoDefault, EvtIoDefault callback function, kmdf.evtiodefault, wdf.evtiodefault, wdfio/EvtIoDefault
f1_keywords:
 - "wdfio/EvtIoDefault"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfio.h
api_name:
- EvtIoDefault
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_DEFAULT callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoDefault</i> event callback function processes a specified I/O request.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


## -remarks



A driver registers an <i>EvtIoDefault</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoDefault</i> callback function for a device's I/O queue, the callback function receives every I/O request from the queue, unless request-specific callback functions have also been registered. For more information about request-specific callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>. 

A driver's <i>EvtIoDefault</i> callback function can also receive file creation requests. For more information about receiving file creation requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.

The <i>EvtIoDefault</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Most I/O operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoDefault</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrainsynchronously">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestopsynchronously">WdfIoQueueStopSynchronously</a>
</dd>
</dl>






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
 

 

