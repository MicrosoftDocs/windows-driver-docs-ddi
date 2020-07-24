---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_WRITE
title: EVT_WDF_IO_QUEUE_IO_WRITE (wdfio.h)
description: A driver's EvtIoWrite event callback function processes a specified write request.
old-location: wdf\evtiowrite.htm
tech.root: wdf
ms.assetid: 5a0fa3b4-d020-4664-afa4-352573d4f079
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_QUEUE_IO_WRITE callback function"]
ms.keywords: DFQueueObjectRef_c98601af-48d0-4fc1-9947-b94c50f7a994.xml, EVT_WDF_IO_QUEUE_IO_WRITE, EVT_WDF_IO_QUEUE_IO_WRITE callback, EvtIoWrite, EvtIoWrite callback function, kmdf.evtiowrite, wdf.evtiowrite, wdfio/EvtIoWrite
f1_keywords:
 - "wdfio/EvtIoWrite"
 - "EvtIoWrite"
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
- EvtIoWrite
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_WRITE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoWrite</i> event callback function processes a specified write request.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


### -param Length [in]

The number of bytes to be written.


## -remarks



A driver registers an <i>EvtIoWrite</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoWrite</i> callback function for a device's I/O queue, the callback function receives every write request from the queue. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoWrite</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Write requests require an input buffer, which contains data that the driver receives. For information about how the driver can access a write request's buffer, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoWrite</i> callback function should not call the following queue object methods:<dl>
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
 

 

