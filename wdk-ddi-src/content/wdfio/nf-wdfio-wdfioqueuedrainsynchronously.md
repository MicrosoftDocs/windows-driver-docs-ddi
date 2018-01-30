---
UID: NF:wdfio.WdfIoQueueDrainSynchronously
title: WdfIoQueueDrainSynchronously function
author: windows-driver-content
description: The WdfIoQueueDrainSynchronously method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled.
old-location: wdf\wdfioqueuedrainsynchronously.htm
old-project: wdf
ms.assetid: e8e53a6d-8b8b-49ed-947b-d0bb69a4d050
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueDrainSynchronously method, WdfIoQueueDrainSynchronously, PFN_WDFIOQUEUEDRAINSYNCHRONOUSLY, DFQueueObjectRef_8c2d977e-f24a-49b8-bb80-e4b3d369d23a.xml, wdf.wdfioqueuedrainsynchronously, kmdf.wdfioqueuedrainsynchronously, wdfio/WdfIoQueueDrainSynchronously
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
req.irql: PASSIVE_LEVEL
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
-	WdfIoQueueDrainSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueDrainSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueDrainSynchronously</b> method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled.


## -syntax


````
VOID WdfIoQueueDrainSynchronously(
  _In_ WDFQUEUE Queue
);
````


## -parameters




### -param Queue [in]

A handle to a framework queue object.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After a driver calls <b>WdfIoQueueDrainSynchronously</b>, the framework stops adding I/O requests to the specified queue. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

The driver should not call another method that changes queue state, such as <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a> or <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>, before the call to <b>WdfIoQueueDrainSynchronously</b> has returned.

As a best practice, you should only call <b>WdfIoQueueDrainSynchronously</b> when you are certain that the queue's pending I/O requests will complete in a timely fashion. Otherwise, use <a href="..\wdfio\nf-wdfio-wdfioqueuepurgesynchronously.md">WdfIoQueuePurgeSynchronously</a>.  For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

After a driver has drained an I/O queue, it can restart the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueueDrainSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_default.md">EvtIoDefault</a><a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a><a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a><a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a><a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_write.md">EvtIoWrite</a>


## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueDrainSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

