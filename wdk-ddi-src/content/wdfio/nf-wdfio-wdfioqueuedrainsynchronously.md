---
UID: NF:wdfio.WdfIoQueueDrainSynchronously
title: WdfIoQueueDrainSynchronously function
author: windows-driver-content
description: The WdfIoQueueDrainSynchronously method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed. The method returns after all requests are completed or canceled.
old-location: wdf\wdfioqueuedrainsynchronously.htm
tech.root: wdf
ms.assetid: e8e53a6d-8b8b-49ed-947b-d0bb69a4d050
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_8c2d977e-f24a-49b8-bb80-e4b3d369d23a.xml, WdfIoQueueDrainSynchronously, WdfIoQueueDrainSynchronously method, kmdf.wdfioqueuedrainsynchronously, wdf.wdfioqueuedrainsynchronously, wdfio/WdfIoQueueDrainSynchronously
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
-	WdfIoQueueDrainSynchronously
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


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver calls <b>WdfIoQueueDrainSynchronously</b>, the framework stops adding I/O requests to the specified queue. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

The driver should not call another method that changes queue state, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff548442">WdfIoQueuePurge</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a>, before the call to <b>WdfIoQueueDrainSynchronously</b> has returned.

As a best practice, you should only call <b>WdfIoQueueDrainSynchronously</b> when you are certain that the queue's pending I/O requests will complete in a timely fashion. Otherwise, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff548449">WdfIoQueuePurgeSynchronously</a>.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

After a driver has drained an I/O queue, it can restart the queue by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueueDrainSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

<a href="https://msdn.microsoft.com/0b834d01-5603-43e8-9b74-9292610cc06d">EvtIoDefault</a>
<a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a>
<a href="https://msdn.microsoft.com/268d2323-57a3-4674-90e6-d7142804175b">EvtIoInternalDeviceControl</a>
<a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a>
<a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a>

#### Examples

The following code example drains an I/O queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfIoQueueDrainSynchronously(queue);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547406">WdfIoQueueDrain</a>
 

 

