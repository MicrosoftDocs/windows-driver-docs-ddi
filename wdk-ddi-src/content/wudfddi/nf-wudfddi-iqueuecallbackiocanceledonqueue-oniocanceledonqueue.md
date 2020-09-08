---
UID: NF:wudfddi.IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue
title: IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue (wudfddi.h)
description: A driver's OnIoCanceledOnQueue event callback function informs the driver that an I/O request was canceled while it was in an I/O queue.
old-location: wdf\iqueuecallbackiocanceledonqueue_oniocanceledonqueue.htm
tech.root: wdf
ms.assetid: 901ff312-d1bb-46bf-b8e6-6abc47fa3c7f
ms.date: 02/26/2018
keywords: ["IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue"]
ms.keywords: IQueueCallbackIoCanceledOnQueue interface,OnIoCanceledOnQueue method, IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue, IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue, OnIoCanceledOnQueue, OnIoCanceledOnQueue method, OnIoCanceledOnQueue method,IQueueCallbackIoCanceledOnQueue interface, UMDFQueueObjectRef_e80a1257-b51e-46f8-8e9f-0fff3b830587.xml, umdf.iqueuecallbackiocanceledonqueue_oniocanceledonqueue, wdf.iqueuecallbackiocanceledonqueue_oniocanceledonqueue, wudfddi/IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue
 - wudfddi/IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue
---

# IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnIoCanceledOnQueue</b> event callback function informs the driver that an I/O request was canceled while it was in an I/O queue.

## -parameters

### -param pWdfQueue 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue that the I/O request was in when it was canceled.

### -param pWdfRequest 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the I/O request.

## -remarks

A driver registers an I/O queue's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackiocanceledonqueue">IQueueCallbackIoCanceledOnQueue</a> interface and <b>OnIoCanceledOnQueue</b> callback function when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>. For more information about how to register the interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackiocanceledonqueue">IQueueCallbackIoCanceledOnQueue</a>.

If a driver registers an <b>OnIoCanceledOnQueue</b> callback function for an I/O queue, the framework calls the callback function if a request handler receives an I/O request from an I/O queue, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-requeue">IWDFIoRequest2::Requeue</a> to requeue the request to the I/O queue for which the <b>OnIoCanceledOnQueue</b> callback function is registered, and the associated I/O operation is subsequently canceled.

After the framework calls the <b>OnIoCanceledOnQueue</b> callback function, the driver owns the request object and, therefore, must <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> the request.

The framework does not call the driver's <b>OnIoCanceledOnQueue</b> callback function for I/O requests that the framework has never delivered to the driver.

The framework calls an <b>OnIoCanceledOnQueue</b> callback function as soon as it determines that an I/O request has been canceled, regardless of the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">dispatching method</a> that the driver has set for the I/O queue. Therefore, the framework can call an <b>OnIoCanceledOnQueue</b> callback function for a request in a queue that uses sequential dispatching, even if the driver currently owns another request from the queue.

For more information about the <b>OnIoCanceledOnQueue</b> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackiocanceledonqueue">IQueueCallbackIoCanceledOnQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a>

