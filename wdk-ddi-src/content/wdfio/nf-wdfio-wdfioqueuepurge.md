---
UID: NF:wdfio.WdfIoQueuePurge
title: WdfIoQueuePurge function
author: windows-driver-content
description: The WdfIoQueuePurge method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests.
old-location: wdf\wdfioqueuepurge.htm
old-project: wdf
ms.assetid: bd6e9583-774f-4ca2-9c23-4d32b233daff
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFIOQUEUEPURGE, wdfio/WdfIoQueuePurge, kmdf.wdfioqueuepurge, wdf.wdfioqueuepurge, WdfIoQueuePurge, WdfIoQueuePurge method, DFQueueObjectRef_611371f2-862e-41c5-9f8f-d0a61c7e731e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfIoQueuePurge
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueuePurge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueuePurge</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests. 


## -syntax


````
VOID WdfIoQueuePurge(
  _In_     WDFQUEUE               Queue,
  _In_opt_ PFN_WDF_IO_QUEUE_STATE PurgeComplete,
  _In_opt_ WDFCONTEXT             Context
);
````


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param PurgeComplete [in, optional]

A pointer to a driver-supplied <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After a driver calls <b>WdfIoQueuePurge</b>, the framework stops adding I/O requests to the specified queue. The framework <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all requests that it has not delivered to the target device and calls the driver's  <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function  for each. The framework also attempts to cancel (by calling <a href="..\wdm\nf-wdm-iocancelirp.md">IoCancelIrp</a>) any requests delivered to the target device that were not marked <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</a>.

If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

If the driver supplies an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

If the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestrequeue.md">WdfRequestRequeue</a> after calling <b>WdfIoQueuePurge</b>, the requeue attempt may succeed before the purge is complete. In versions 1.9 and earlier of KMDF, this 
sequence causes the operating system to crash.  This problem is fixed in KMDF version 1.11 and later.

For more information about the <b>WdfIoQueuePurge</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuepurgesynchronously.md">WdfIoQueuePurgeSynchronously</a>

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueuePurge method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

