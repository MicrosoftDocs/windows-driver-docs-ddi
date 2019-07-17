---
UID: NF:wdfio.WdfIoQueueStopSynchronously
title: WdfIoQueueStopSynchronously function (wdfio.h)
description: The WdfIoQueueStopSynchronously method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.
old-location: wdf\wdfioqueuestopsynchronously.htm
tech.root: wdf
ms.assetid: b92072a6-fa6e-4b8d-83c3-b2844443f5c8
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_9f415317-56ca-4c4f-9f33-560258351999.xml, WdfIoQueueStopSynchronously, WdfIoQueueStopSynchronously method, kmdf.wdfioqueuestopsynchronously, wdf.wdfioqueuestopsynchronously, wdfio/WdfIoQueueStopSynchronously
ms.topic: function
f1_keywords:
 - "wdfio/WdfIoQueueStopSynchronously"
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
- WdfIoQueueStopSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueStopSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoQueueStopSynchronously</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoQueueStopSynchronously</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>WdfIoQueueStopSynchronously</b>. For example, a driver might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuedrain">WdfIoQueueDrain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>WdfIoQueueStopSynchronously</b> causes the framework to resume adding requests to the queue.

Do not call <b>WdfIoQueueStopSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_internal_device_control">EvtIoInternalDeviceControl</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a>
For more information about the <b>WdfIoQueueStopSynchronously</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example stops a specified queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfIoQueueStopSynchronously(WriteQueue);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nf-wdfio-wdfioqueuestop">WdfIoQueueStop</a>
 

 

