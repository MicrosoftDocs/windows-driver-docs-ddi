---
UID: NF:wudfddi.IWDFIoRequest.Complete
title: IWDFIoRequest::Complete method
author: windows-driver-content
description: The Complete method completes an I/O request.
old-location: wdf\iwdfiorequest_complete.htm
old-project: wdf
ms.assetid: 2fa389f8-8277-4795-a89e-ac5d92004310
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Complete method, Complete method, IWDFIoRequest interface, Complete,IWDFIoRequest.Complete, IWDFIoRequest, IWDFIoRequest interface, Complete method, IWDFIoRequest::Complete, UMDFRequestObjectRef_2c1cf2cc-30a2-438c-8e5a-b918fbcd5eee.xml, umdf.iwdfiorequest_complete, wdf.iwdfiorequest_complete, wudfddi/IWDFIoRequest::Complete
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
-	IWDFIoRequest.Complete
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::Complete method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Complete</b> method completes an I/O request.


## -parameters




### -param CompletionStatus [in]

A status value to complete the request with. 


## -returns



None




## -remarks



Instead of calling <b>Complete</b>, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a> method.

For more information about completing an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


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
 
    FxRequest-&gt;GetInputMemory(&amp;FxInputMemory);
    if (S_OK != hr) {
        FxRequest-&gt;Complete(hr);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a>
 

 

