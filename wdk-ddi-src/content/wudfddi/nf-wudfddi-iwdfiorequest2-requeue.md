---
UID: NF:wudfddi.IWDFIoRequest2.Requeue
title: IWDFIoRequest2::Requeue (wudfddi.h)
description: The Requeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.
old-location: wdf\iwdfiorequest2_requeue.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::Requeue"]
ms.keywords: IWDFIoRequest2 interface,Requeue method, IWDFIoRequest2.Requeue, IWDFIoRequest2::Requeue, Requeue, Requeue method, Requeue method,IWDFIoRequest2 interface, UMDFRequestObjectRef_e86bd6e8-ed4b-42e8-a32f-29c4415e1384.xml, umdf.iwdfiorequest2_requeue, wdf.iwdfiorequest2_requeue, wudfddi/IWDFIoRequest2::Requeue
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
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest2::Requeue
 - wudfddi/IWDFIoRequest2::Requeue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2::Requeue
---

# IWDFIoRequest2::Requeue


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Requeue</b> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.

## -returns

<b>Requeue</b> returns S_OK if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_OPERATION)</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>
The specified I/O request did not come from an I/O queue.

</li>
<li>
The driver does not own the I/O request.

</li>
<li>
The request is cancelable.

</li>
<li>
The queue's dispatching method is not manual.

</li>
</ul>
</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

A driver can call <b>Requeue</b> only if it uses the <a href="/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">manual dispatching method</a> for the I/O queue.


#### Examples

The following code example shows a segment of an <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackstatechange-onstatechange">IQueueCallbackStateChange::OnStateChange</a> callback function. The segment obtains an I/O request from the I/O and then returns the request to the queue.


```
void 
CMyQueue::OnStateChange(
    __in IWDFIoQueue* pWdfQueue,
    __in WDF_IO_QUEUE_STATE 
    )
{
    HRESULT hr;
    IWDFIoRequest* Request;
...
    //
    // Get the IWDFIoRequest interface of the next request.
    //
    hr = pWdfQueue->RetrieveNextRequest(&Request);
...
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = Request;

    //
    // Add code here to determine whether to process or requeue the request.
    //
...
    //
    // Requeue the request.
    //
    hr = r2->Requeue();
    if (FAILED(hr)) goto Error;
...
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>

