---
UID: NF:wdfio.WdfIoQueuePurge
title: WdfIoQueuePurge function (wdfio.h)
description: The WdfIoQueuePurge method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests.
old-location: wdf\wdfioqueuepurge.htm
tech.root: wdf
ms.assetid: bd6e9583-774f-4ca2-9c23-4d32b233daff
ms.date: 02/26/2018
keywords: ["WdfIoQueuePurge function"]
ms.keywords: DFQueueObjectRef_611371f2-862e-41c5-9f8f-d0a61c7e731e.xml, WdfIoQueuePurge, WdfIoQueuePurge method, kmdf.wdfioqueuepurge, wdf.wdfioqueuepurge, wdfio/WdfIoQueuePurge
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
 - WdfIoQueuePurge
 - wdfio/WdfIoQueuePurge
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
 - WdfIoQueuePurge
---

# WdfIoQueuePurge function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueuePurge</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests.

## -parameters

### -param Queue 

[in]
A handle to a framework queue object.

### -param PurgeComplete 

[in, optional]
A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.

### -param Context 

[in, optional]
An untyped pointer to driver-supplied context information that the framework passes to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver calls <b>WdfIoQueuePurge</b>, the framework stops adding I/O requests to the specified queue. The framework <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all requests that it has not delivered to the target device and calls the driver's  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function  for each. The framework also attempts to cancel (by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp">IoCancelIrp</a>) any requests delivered to the target device that were not marked <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</a>.

If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

If the driver supplies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled. You can modify the IRQL at which the callback runs by specifying **ExecutionLevel** in [WDF_OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) at queue creation time. For more info, see the Remarks section of[*EVT_WDF_IO_QUEUE_STATE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state).

After a driver has purged an I/O queue, it can restart the queue by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>.

If the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestrequeue">WdfRequestRequeue</a> after calling <b>WdfIoQueuePurge</b>, the requeue attempt may succeed before the purge is complete. In versions 1.9 and earlier of KMDF, this 
sequence causes the operating system to crash.  This problem is fixed in KMDF version 1.11 and later.

For more information about the <b>WdfIoQueuePurge</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example purges an I/O queue and does not call a callback function when all requests that were delivered to the driver have been completed or canceled.

```cpp
WdfIoQueuePurge(
                ReadQueue, 
                WDF_NO_EVENT_CALLBACK, 
                WDF_NO_CONTEXT 
                );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_state">EvtIoQueueState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuedrain">WdfIoQueueDrain</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuepurgesynchronously">WdfIoQueuePurgeSynchronously</a>

