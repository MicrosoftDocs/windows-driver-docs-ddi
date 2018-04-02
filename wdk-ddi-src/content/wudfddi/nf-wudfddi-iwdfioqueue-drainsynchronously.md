---
UID: NF:wudfddi.IWDFIoQueue.DrainSynchronously
title: IWDFIoQueue::DrainSynchronously method
author: windows-driver-content
description: The DrainSynchronously method directs the queue to reject new incoming I/O requests and allows already-queued requests to be delivered to the driver for processing. This method returns after all requests are completed or canceled.
old-location: wdf\iwdfioqueue_drainsynchronously.htm
old-project: wdf
ms.assetid: 6dc32dd7-e15b-4c93-92d1-5b7206ed98c0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrainSynchronously method, DrainSynchronously method, IWDFIoQueue interface, DrainSynchronously,IWDFIoQueue.DrainSynchronously, IWDFIoQueue, IWDFIoQueue interface, DrainSynchronously method, IWDFIoQueue::DrainSynchronously, UMDFQueueObjectRef_35105420-0461-4879-aba2-28c32ece9aab.xml, umdf.iwdfioqueue_drainsynchronously, wdf.iwdfioqueue_drainsynchronously, wudfddi/IWDFIoQueue::DrainSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoQueue.DrainSynchronously
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::DrainSynchronously method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DrainSynchronously</b> method directs the queue to reject new incoming I/O requests and allows already-queued requests to be delivered to the driver for processing. This method returns after all requests are completed or canceled.


## -parameters






## -returns



None




## -remarks



The <b>DrainSynchronously</b> method is a synchronous version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a> method. That is, <b>DrainSynchronously</b> does not return to the driver until the queue is drained.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>
 

 

