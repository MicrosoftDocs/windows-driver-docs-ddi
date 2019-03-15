---
UID: NF:wdfio.WdfIoQueueStopAndPurge
title: WdfIoQueueStopAndPurge function (wdfio.h)
description: The WdfIoQueueStopAndPurge method prevents an I/O queue from delivering new requests and cancels existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests.
old-location: wdf\wdfioqueuestopandpurge.htm
tech.root: wdf
ms.assetid: 3A9CF1BD-77F1-4F4C-AEB5-0E77B67C45D3
ms.date: 02/26/2018
ms.keywords: WdfIoQueueStopAndPurge, WdfIoQueueStopAndPurge method, kmdf.wdfioqueuestopandpurge, wdf.wdfioqueuestopandpurge, wdfio/WdfIoQueueStopAndPurge
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, NoCancelFromEvtSurpriseRemove
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
- WdfIoQueueStopAndPurge
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueStopAndPurge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The <b>WdfIoQueueStopAndPurge</b> method prevents an I/O queue from delivering new requests and cancels existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param StopAndPurgeComplete [in, optional]

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function. This parameter is optional and can be NULL.


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function. This parameter is optional and can be NULL.


## -returns



This method does not return a value.




## -remarks




   The <b>WdfIoQueueStopAndPurge</b> method prevents an I/O queue from delivering I/O requests to the driver while allowing new requests to be added to the queue.
  In addition, it cancels unprocessed requests in the queue and driver-owned cancellable requests (requests that were delivered to the driver that driver has not completed or requeued). If new requests are added while <b>WdfIoQueueStopAndPurge</b> is in progress, these new requests are not delivered until driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a>.

In contrast, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548482">WdfIoQueueStop</a> method does not cancel unprocessed requests in the queue or driver-owned cancellable requests.

If this method causes the framework to cancel an unprocessed request in a queue, the framework calls the driver's <a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a> callback function for that queue, if the driver has supplied one.


    If the driver supplies an <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

The <b>WdfIoQueueStopAndPurge</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>WdfIoQueueStopAndPurge</b>. For example, a driver might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547406">WdfIoQueueDrain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>WdfIoQueueStopAndPurge</b> causes the framework to resume adding requests to the queue.


In contrast, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548442">WdfIoQueuePurge</a> causes the framework to stop adding I/O requests to the specified queue.

A bug check occurs if the driver supplies an invalid object handle.


#### Examples

The following code example stops and purges a specified I/O queue. After all requests that were delivered to the driver have been completed or canceled, the framework calls a driver's EvtIoQueueStateStopAndPurge function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFCONTEXT stopandpurgeContext;

stopandpurgeContext = &amp;myContext;

WdfIoQueueStopAndPurge(
               queue,
               EvtIoQueueStateStopAndPurge,
               stopandpurgeContext
               );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a>



<a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439293">WdfIoQueueStopAndPurgeSynchronously</a>
 

 

