---
UID: NF:wudfddi.IWDFIoRequest.Complete
title: IWDFIoRequest::Complete (wudfddi.h)
description: The Complete method completes an I/O request.
old-location: wdf\iwdfiorequest_complete.htm
tech.root: wdf
ms.assetid: 2fa389f8-8277-4795-a89e-ac5d92004310
ms.date: 02/26/2018
ms.keywords: Complete, Complete method, Complete method,IWDFIoRequest interface, IWDFIoRequest interface,Complete method, IWDFIoRequest.Complete, IWDFIoRequest::Complete, UMDFRequestObjectRef_2c1cf2cc-30a2-438c-8e5a-b918fbcd5eee.xml, umdf.iwdfiorequest_complete, wdf.iwdfiorequest_complete, wudfddi/IWDFIoRequest::Complete
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest.Complete"
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
- IWDFIoRequest.Complete
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::Complete


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Complete</b> method completes an I/O request.


## -parameters




### -param CompletionStatus [in]

A status value to complete the request with. 


## -returns



None




## -remarks



Instead of calling <b>Complete</b>, the driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-completewithinformation">IWDFIoRequest::CompleteWithInformation</a> method.

For more information about completing an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example completes a request with the failure that occurred when a memory object could not be retrieved.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    IWDFIoRequest* FxRequest;
    HRESULT hr = S_OK;
    IWDFMemory* FxInputMemory = NULL;
 
    FxRequest->GetInputMemory(&FxInputMemory);
    if (S_OK != hr) {
        FxRequest->Complete(hr);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-completewithinformation">IWDFIoRequest::CompleteWithInformation</a>
 

 

