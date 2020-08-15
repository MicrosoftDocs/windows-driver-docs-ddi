---
UID: NF:wdfio.WdfIoQueuePurgeSynchronously
title: WdfIoQueuePurgeSynchronously function (wdfio.h)
description: The WdfIoQueuePurgeSynchronously method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.
old-location: wdf\wdfioqueuepurgesynchronously.htm
tech.root: wdf
ms.assetid: 705faf80-79c4-4f2a-a399-d9a26bde54cf
ms.date: 02/26/2018
keywords: ["WdfIoQueuePurgeSynchronously function"]
ms.keywords: DFQueueObjectRef_3630b28a-48ff-4b9d-9359-9b88771e5104.xml, WdfIoQueuePurgeSynchronously, WdfIoQueuePurgeSynchronously method, kmdf.wdfioqueuepurgesynchronously, wdf.wdfioqueuepurgesynchronously, wdfio/WdfIoQueuePurgeSynchronously
f1_keywords:
 - "wdfio/WdfIoQueuePurgeSynchronously"
 - "WdfIoQueuePurgeSynchronously"
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
- WdfIoQueuePurgeSynchronously
targetos: Windows
req.typenames: 
---

# WdfIoQueuePurgeSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueuePurgeSynchronously</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.


## -parameters




### -param Queue 
[in]
A handle to a framework queue object.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver calls <b>WdfIoQueuePurgeSynchronously</b>, the framework stops adding I/O requests to the specified queue. The framework cancels all requests that it has not delivered to the driver. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

<b>WdfIoQueuePurgeSynchronously</b> returns after all the unprocessed and driver-owned requests are completed or canceled.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueuePurgeSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>
For more information about the <b>WdfIoQueuePurgeSynchronously</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example purges a specified I/O queue.

```cpp
WdfIoQueuePurgeSynchronously(ReadQueue);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurge">WdfIoQueuePurge</a>
 

 

