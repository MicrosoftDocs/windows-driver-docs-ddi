---
UID: NF:wdfio.WdfIoQueueDrain
title: WdfIoQueueDrain function (wdfio.h)
description: The WdfIoQueueDrain method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed.
old-location: wdf\wdfioqueuedrain.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfIoQueueDrain function"]
ms.keywords: DFQueueObjectRef_39ca90c2-1fc9-4f1c-b05f-d46f668a3cd1.xml, WdfIoQueueDrain, WdfIoQueueDrain method, kmdf.wdfioqueuedrain, wdf.wdfioqueuedrain, wdfio/WdfIoQueueDrain
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoQueueDrain
 - wdfio/WdfIoQueueDrain
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfIoQueueDrain
---

# WdfIoQueueDrain function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueDrain</b> method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed.

## -parameters

### -param Queue [in]


A handle to a framework queue object.

### -param DrainComplete [in, optional]


A pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.

### -param Context [in, optional]


An untyped pointer to driver-supplied context information that the framework passes to the <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver calls <b>WdfIoQueueDrain</b>, the framework stops adding I/O requests to the specified queue. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

If the driver supplies an <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled. You can modify the IRQL at which the callback runs by specifying **ExecutionLevel** in [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) at queue creation time. For more info, see the Remarks section of[*EVT_WDF_IO_QUEUE_STATE*](./nc-wdfio-evt_wdf_io_queue_state.md).

The driver should not call another method that changes queue state, such as <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a> or <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>, before the framework has called <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a>.

If a driver specifies <b>NULL</b> for <i>DrainComplete</i>, the driver can call another state changing operation before requests are completed.

As a best practice, you should only call <b>WdfIoQueueDrain</b> when you are certain that the queue's pending I/O requests will complete in a timely fashion. Otherwise, use <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>. For more information, see <a href="/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

After a driver has drained an I/O queue, it can restart the queue by calling <a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>.


#### Examples

The following code example drains an I/O queue and calls a driver's <b>EvtIoQueueDrainComplete</b> function when all requests that were delivered to the driver have been completed or canceled.

```cpp
WdfIoQueueDrain(
                Queue,
                EvtIoQueueDrainComplete,
                (WDFCONTEXT) myQueueContext
                );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrainsynchronously">WdfIoQueueDrainSynchronously</a>



<a href="/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>
