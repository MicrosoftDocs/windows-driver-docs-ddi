---
UID: NF:wdfio.WdfIoQueueStopSynchronously
title: WdfIoQueueStopSynchronously function
author: windows-driver-content
description: The WdfIoQueueStopSynchronously method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.
old-location: wdf\wdfioqueuestopsynchronously.htm
old-project: wdf
ms.assetid: b92072a6-fa6e-4b8d-83c3-b2844443f5c8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueStopSynchronously
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
req.alt-api: WdfIoQueueStopSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueStopSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueStopSynchronously</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.



## -syntax

````
VOID WdfIoQueueStopSynchronously(
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
The <b>WdfIoQueueStopSynchronously</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>WdfIoQueueStopSynchronously</b>. For example, a driver might call <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>WdfIoQueueStopSynchronously</b> causes the framework to resume adding requests to the queue.

Do not call <b>WdfIoQueueStopSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

For more information about the <b>WdfIoQueueStopSynchronously</b> method, see <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

The following code example stops a specified queue.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuestop.md">WdfIoQueueStop</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueStopSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

