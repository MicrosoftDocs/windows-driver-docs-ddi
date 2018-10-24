---
UID: NF:wudfddi.IWDFIoRequest2.Requeue
title: IWDFIoRequest2::Requeue
author: windows-driver-content
description: The Requeue method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.
old-location: wdf\iwdfiorequest2_requeue.htm
tech.root: wdf
ms.assetid: 1e33f284-6cb9-426f-a900-76b827341927
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2 interface,Requeue method, IWDFIoRequest2.Requeue, IWDFIoRequest2::Requeue, Requeue, Requeue method, Requeue method,IWDFIoRequest2 interface, UMDFRequestObjectRef_e86bd6e8-ed4b-42e8-a32f-29c4415e1384.xml, umdf.iwdfiorequest2_requeue, wdf.iwdfiorequest2_requeue, wudfddi/IWDFIoRequest2::Requeue
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest2.Requeue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::Requeue


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Requeue</b> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.


## -parameters






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



A driver can call <b>Requeue</b> only if it uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">manual dispatching method</a> for the I/O queue.


#### Examples

The following code example shows a segment of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556880">IQueueCallbackStateChange::OnStateChange</a> callback function. The segment obtains an I/O request from the I/O and then returns the request to the queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void 
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
    hr = pWdfQueue-&gt;RetrieveNextRequest(&amp;Request);
...
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr&lt;IWDFIoRequest2&gt; r2 = Request;

    //
    // Add code here to determine whether to process or requeue the request.
    //
...
    //
    // Requeue the request.
    //
    hr = r2-&gt;Requeue();
    if (FAILED(hr)) goto Error;
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>
 

 

