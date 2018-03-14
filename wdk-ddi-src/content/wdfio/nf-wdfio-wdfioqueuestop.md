---
UID: NF:wdfio.WdfIoQueueStop
title: WdfIoQueueStop function
author: windows-driver-content
description: The WdfIoQueueStop method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.
old-location: wdf\wdfioqueuestop.htm
old-project: wdf
ms.assetid: 50ff8064-b28c-4b2b-89d2-bad5e503b2d6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_c1ac397c-5601-4976-9c42-41b118d429c1.xml, WdfIoQueueStop, WdfIoQueueStop method, kmdf.wdfioqueuestop, wdf.wdfioqueuestop, wdfio/WdfIoQueueStop
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
-	WdfIoQueueStop
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueStop function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueStop</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.


## -syntax


````
VOID WdfIoQueueStop(
  _In_     WDFQUEUE               Queue,
  _In_opt_ PFN_WDF_IO_QUEUE_STATE StopComplete,
  _In_opt_ WDFCONTEXT             Context
);
````


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param StopComplete [in, optional]

A pointer to a driver-supplied <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the driver supplies an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

The <b>WdfIoQueueStop</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>WdfIoQueueStop</b>. For example, before calling <b>WdfIoQueueStop</b>, a driver might call <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>WdfIoQueueStop</b> causes the framework to resume adding requests to the queue.

A driver must not call <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a> after calling <b>WdfIoQueueStop</b> until it has restarted the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

For more information about the <b>WdfIoQueueStop</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example stops a specified I/O queue. When all requests that were delivered to the driver have been completed or canceled, it calls a driver's <b>EvtIoQueueStateStop</b> function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFCONTEXT stopContext;

stopContext = &amp;myContext;

WdfIoQueueStop(
               queue,
               EvtIoQueueStateStop,
               stopContext
               );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuestopsynchronously.md">WdfIoQueueStopSynchronously</a>



<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a>



 

 


