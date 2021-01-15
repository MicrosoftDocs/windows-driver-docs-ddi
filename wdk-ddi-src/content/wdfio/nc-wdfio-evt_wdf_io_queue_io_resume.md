---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_RESUME
title: EVT_WDF_IO_QUEUE_IO_RESUME (wdfio.h)
description: A driver's EvtIoResume event callback function resumes processing a specified I/O request after the underlying device returns to its working (D0) power state.
old-location: wdf\evtioresume.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_IO_QUEUE_IO_RESUME callback function"]
ms.keywords: DFQueueObjectRef_1ecb2f86-9461-47b7-967d-6cb14edbbe82.xml, EVT_WDF_IO_QUEUE_IO_RESUME, EVT_WDF_IO_QUEUE_IO_RESUME callback, EvtIoResume, EvtIoResume callback function, kmdf.evtioresume, wdf.evtioresume, wdfio/EvtIoResume
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
 - EVT_WDF_IO_QUEUE_IO_RESUME
 - wdfio/EVT_WDF_IO_QUEUE_IO_RESUME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfio.h
api_name:
 - EVT_WDF_IO_QUEUE_IO_RESUME
---

# EVT_WDF_IO_QUEUE_IO_RESUME callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoResume</i> event callback function resumes processing a specified I/O request after the underlying device returns to its working (D0) power state.

## -parameters

### -param Queue 

[in]
A handle to the framework queue object that is associated with the I/O request.

### -param Request 

[in]
A handle to a framework request object.

## -remarks

A driver registers an <i>EvtIoResume</i> callback function when it calls the <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a> method. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

A driver registers <i>EvtIoResume</i> only for use with a power-managed queue.

The framework calls the driver's <i>EvtIoResume</i> callback function only if the driver's <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_stop">EvtIoStop</a> callback function previously called <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequeststopacknowledge">WdfRequestStopAcknowledge</a> with the <i>Requeue</i> parameter set to <b>FALSE</b>.

For more information about the <i>EvtIoResume</i> callback function, see <a href="/windows-hardware/drivers/wdf/using-power-managed-i-o-queues">Using Power-Managed I/O Queues</a>.

This callback function can be called at IRQL <= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>. You should not make this callback function <a href="/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuecreate">WdfIoQueueCreate</a>

