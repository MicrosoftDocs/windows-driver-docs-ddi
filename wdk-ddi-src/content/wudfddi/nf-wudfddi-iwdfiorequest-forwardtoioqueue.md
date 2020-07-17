---
UID: NF:wudfddi.IWDFIoRequest.ForwardToIoQueue
title: IWDFIoRequest::ForwardToIoQueue (wudfddi.h)
description: The ForwardToIoQueue method forwards (that is, requeues) an I/O request to one of the calling driver's I/O queues.
old-location: wdf\iwdfiorequest_forwardtoioqueue.htm
tech.root: wdf
ms.assetid: 07317157-1222-4b34-89f4-d546818e9851
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::ForwardToIoQueue"]
ms.keywords: ForwardToIoQueue, ForwardToIoQueue method, ForwardToIoQueue method,IWDFIoRequest interface, IWDFIoRequest interface,ForwardToIoQueue method, IWDFIoRequest.ForwardToIoQueue, IWDFIoRequest::ForwardToIoQueue, UMDFRequestObjectRef_ae3c7113-1fac-4742-b53b-8230bf78b61a.xml, umdf.iwdfiorequest_forwardtoioqueue, wdf.iwdfiorequest_forwardtoioqueue, wudfddi/IWDFIoRequest::ForwardToIoQueue
f1_keywords:
 - "wudfddi/IWDFIoRequest.ForwardToIoQueue"
 - "IWDFIoRequest.ForwardToIoQueue"
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
- IWDFIoRequest.ForwardToIoQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::ForwardToIoQueue


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ForwardToIoQueue</b> method forwards (that is, requeues) an I/O request to one of the calling driver's I/O queues.


## -parameters




### -param pDestination [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the destination queue object.


## -returns



<b>ForwardToIoQueue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The driver must own the I/O request and must have obtained the request from one of its I/O queues.

The source and destination queues cannot be the same. In other words, the driver cannot call <b>ForwardToIoQueue</b> to return a request to the queue that it came from. To return an I/O request to the I/O queue that it came from, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-requeue">IWDFIoRequest2::Requeue</a>.

Both the source and destination queues must belong to the same device.

Also, the <b>ForwardToIoQueue</b> method cannot requeue a request that the driver obtained by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a> method.

The request cannot be cancelable. If the driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> method to make the request cancelable, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a> method before calling <b>ForwardToIoQueue</b>.


#### Examples

The following code example shows how to forward a request to another queue if the request's buffer is insufficient to hold the required information.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT hr;
 if (OutputBufferSizeInBytes < sizeof(SWITCH_STATE)) {
    hr = HRESULT_FROM_NT(ERROR_INSUFFICIENT_BUFFER);
 }
 else {
     hr = FxRequest->ForwardToIoQueue(
                          m_Device->GetSwitchChangeQueue()
                          );
     if (SUCCEEDED(hr)) {
         completeRequest = false;
     }
  }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a>
 

 

