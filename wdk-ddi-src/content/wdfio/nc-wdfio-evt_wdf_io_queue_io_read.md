---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_READ
title: EVT_WDF_IO_QUEUE_IO_READ (wdfio.h)
description: A driver's EvtIoRead event callback function processes a specified read request.
old-location: wdf\evtioread.htm
tech.root: wdf
ms.assetid: d6fbb153-1355-4e94-b5d3-a218bd8c565d
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_d5f59efc-e7db-4c3e-9845-5ba0c4949cd5.xml, EVT_WDF_IO_QUEUE_IO_READ, EVT_WDF_IO_QUEUE_IO_READ callback, EvtIoRead, EvtIoRead callback function, kmdf.evtioread, wdf.evtioread, wdfio/EvtIoRead
ms.topic: callback
f1_keywords:
 - "wdfio/EvtIoRead"
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
- EvtIoRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_READ callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoRead</i> event callback function processes a specified read request.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


### -param Length [in]

The number of bytes to be read.


## -remarks



A driver registers an <i>EvtIoRead</i> callback function when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see  <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoRead</i> callback function for a device's I/O queue, the callback function receives every read request from the queue. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoRead</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

Read requests require an output buffer, which receives data that the driver provides. For information about how the driver can access a read request's buffer, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/critical-regions-and-guarded-regions">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoRead</i> callback function should not call the following queue object methods:<dl>
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



#### Examples

To define an <i>EvtIoRead</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoRead</i> callback function that is named <i>MyIoRead</i>, use the <b>EVT_WDF_IO_QUEUE_IO_READ</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_READ  MyIoRead;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyIoRead (
    WDFQUEUE  Queue,
    WDFREQUEST  Request,
    size_t  Length
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_READ</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_READ</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>
 

 

