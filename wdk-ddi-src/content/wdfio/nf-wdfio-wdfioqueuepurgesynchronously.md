---
UID: NF:wdfio.WdfIoQueuePurgeSynchronously
title: WdfIoQueuePurgeSynchronously function
author: windows-driver-content
description: The WdfIoQueuePurgeSynchronously method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.
old-location: wdf\wdfioqueuepurgesynchronously.htm
old-project: wdf
ms.assetid: 705faf80-79c4-4f2a-a399-d9a26bde54cf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_3630b28a-48ff-4b9d-9359-9b88771e5104.xml, WdfIoQueuePurgeSynchronously, WdfIoQueuePurgeSynchronously method, kmdf.wdfioqueuepurgesynchronously, wdf.wdfioqueuepurgesynchronously, wdfio/WdfIoQueuePurgeSynchronously
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoQueuePurgeSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueuePurgeSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueuePurgeSynchronously</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.


## -syntax


````
VOID WdfIoQueuePurgeSynchronously(
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



After a driver calls <b>WdfIoQueuePurgeSynchronously</b>, the framework stops adding I/O requests to the specified queue. The framework cancels all requests that it has not delivered to the driver. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

<b>WdfIoQueuePurgeSynchronously</b> returns after all the unprocessed and driver-owned requests are completed or canceled.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueuePurgeSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_default.md">EvtIoDefault</a>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_write.md">EvtIoWrite</a>
For more information about the <b>WdfIoQueuePurgeSynchronously</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example purges a specified I/O queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfIoQueuePurgeSynchronously(ReadQueue);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>



 

 


