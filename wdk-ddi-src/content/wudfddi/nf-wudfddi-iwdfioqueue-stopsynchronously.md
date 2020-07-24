---
UID: NF:wudfddi.IWDFIoQueue.StopSynchronously
title: IWDFIoQueue::StopSynchronously (wudfddi.h)
description: The StopSynchronously method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.
old-location: wdf\iwdfioqueue_stopsynchronously.htm
tech.root: wdf
ms.assetid: ea05cb82-8a50-48d8-a15c-b7ab58c01b30
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::StopSynchronously"]
ms.keywords: IWDFIoQueue interface,StopSynchronously method, IWDFIoQueue.StopSynchronously, IWDFIoQueue::StopSynchronously, StopSynchronously, StopSynchronously method, StopSynchronously method,IWDFIoQueue interface, UMDFQueueObjectRef_18e42c5a-ade3-4d81-8af1-bd19655650e7.xml, umdf.iwdfioqueue_stopsynchronously, wdf.iwdfioqueue_stopsynchronously, wudfddi/IWDFIoQueue::StopSynchronously
f1_keywords:
 - "wudfddi/IWDFIoQueue.StopSynchronously"
 - "IWDFIoQueue.StopSynchronously"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoQueue.StopSynchronously
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::StopSynchronously


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>StopSynchronously</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.


## -remarks



The <b>StopSynchronously</b> method is the synchronous version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a> method. That is, <b>StopSynchronously</b> does not return to the driver until the queue stops.

The <b>StopSynchronously</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>StopSynchronously</b>. For example, a driver might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>StopSynchronously</b> causes the framework to resume adding requests to the queue.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>
 

 

