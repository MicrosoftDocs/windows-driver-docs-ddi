---
UID: NF:wudfddi.IWDFIoQueue.PurgeSynchronously
title: IWDFIoQueue::PurgeSynchronously (wudfddi.h)
description: The PurgeSynchronously method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests. The method returns after all outstanding requests are canceled.
old-location: wdf\iwdfioqueue_purgesynchronously.htm
tech.root: wdf
ms.assetid: a714dffd-ca88-40cf-95ef-cf15384e0c02
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::PurgeSynchronously"]
ms.keywords: IWDFIoQueue interface,PurgeSynchronously method, IWDFIoQueue.PurgeSynchronously, IWDFIoQueue::PurgeSynchronously, PurgeSynchronously, PurgeSynchronously method, PurgeSynchronously method,IWDFIoQueue interface, UMDFQueueObjectRef_c146c969-5b34-4aa0-af8e-9edec10f4c46.xml, umdf.iwdfioqueue_purgesynchronously, wdf.iwdfioqueue_purgesynchronously, wudfddi/IWDFIoQueue::PurgeSynchronously
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoQueue::PurgeSynchronously
 - wudfddi/IWDFIoQueue::PurgeSynchronously
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoQueue.PurgeSynchronously
---

# IWDFIoQueue::PurgeSynchronously


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>PurgeSynchronously</b> method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests. The method returns after all outstanding requests are canceled.

## -remarks

The framework cancels unprocessed requests in the queue. For requests that are delivered to the driver and marked cancelable, the framework calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>. 

The <b>PurgeSynchronously</b> method is a synchronous version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a> method. That is, <b>PurgeSynchronously</b> does not return to the driver until all outstanding requests are canceled.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a>

