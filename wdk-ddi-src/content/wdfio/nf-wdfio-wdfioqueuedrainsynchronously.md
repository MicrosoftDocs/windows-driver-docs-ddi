---
UID: NF:wdfio.WdfIoQueueDrainSynchronously
title: WdfIoQueueDrainSynchronously function (wdfio.h)
description: The WdfIoQueueDrainSynchronously method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled.
old-location: wdf\wdfioqueuedrainsynchronously.htm
tech.root: wdf
ms.assetid: e8e53a6d-8b8b-49ed-947b-d0bb69a4d050
ms.date: 02/26/2018
keywords: ["WdfIoQueueDrainSynchronously function"]
ms.keywords: DFQueueObjectRef_8c2d977e-f24a-49b8-bb80-e4b3d369d23a.xml, WdfIoQueueDrainSynchronously, WdfIoQueueDrainSynchronously method, kmdf.wdfioqueuedrainsynchronously, wdf.wdfioqueuedrainsynchronously, wdfio/WdfIoQueueDrainSynchronously
f1_keywords:
 - "wdfio/WdfIoQueueDrainSynchronously"
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
req.irql: PASSIVE_LEVEL
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
- WdfIoQueueDrainSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueDrainSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueDrainSynchronously</b> method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver calls <b>WdfIoQueueDrainSynchronously</b>, the framework stops adding I/O requests to the specified queue. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

The driver should not call another method that changes queue state, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>, before the call to <b>WdfIoQueueDrainSynchronously</b> has returned.

As a best practice, you should only call <b>WdfIoQueueDrainSynchronously</b> when you are certain that the queue's pending I/O requests will complete in a timely fashion. Otherwise, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

After a driver has drained an I/O queue, it can restart the queue by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueueDrainSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>

#### Examples

The following code example drains an I/O queue.

```cpp
WdfIoQueueDrainSynchronously(queue);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrain">WdfIoQueueDrain</a>
 

 

