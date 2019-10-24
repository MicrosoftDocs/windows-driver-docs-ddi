---
UID: NF:wdfio.WdfIoQueueStopAndPurgeSynchronously
title: WdfIoQueueStopAndPurgeSynchronously function (wdfio.h)
description: The WdfIoQueueStopAndPurgeSynchronously method prevents an I/O queue from delivering new I/O requests and causes the framework to cancel existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests.
old-location: wdf\wdfioqueuestopandpurgesynchronously.htm
tech.root: wdf
ms.assetid: 406044A5-D1C0-4771-8CDB-CCBC0B801281
ms.date: 02/26/2018
ms.keywords: WdfIoQueueStopAndPurgeSynchronously, WdfIoQueueStopAndPurgeSynchronously method, kmdf.wdfioqueuestopandpurgesynchronously, wdf.wdfioqueuestopandpurgesynchronously, wdfio/WdfIoQueueStopAndPurgeSynchronously
ms.topic: function
f1_keywords:
 - "wdfio/WdfIoQueueStopAndPurgeSynchronously"
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
- WdfIoQueueStopAndPurgeSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueueStopAndPurgeSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>


   The <b>WdfIoQueueStopAndPurgeSynchronously</b> method 
  prevents an I/O queue from delivering new I/O requests and causes the framework to cancel existing unprocessed requests and driver-owned cancellable requests, but the queue receives and stores new requests.


## -parameters




### -param Queue [in]

A handle to a framework queue object.


## -returns



This method does not return a value.




## -remarks



This method returns after all the unprocessed and driver-owned requests (not including requests added to the queue after this call is made) are completed or canceled. If new requests are inserted while <b>WdfIoQueueStopAndPurgeSynchronously</b> is in progress, these new requests are not delivered until driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestart">WdfIoQueueStart</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuestopandpurge">WdfIoQueueStopAndPurge</a>
 

 

