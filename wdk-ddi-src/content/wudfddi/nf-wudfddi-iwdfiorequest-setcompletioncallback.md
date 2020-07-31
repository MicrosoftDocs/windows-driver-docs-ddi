---
UID: NF:wudfddi.IWDFIoRequest.SetCompletionCallback
title: IWDFIoRequest::SetCompletionCallback (wudfddi.h)
description: The SetCompletionCallback method registers the interface for the OnCompletion method that the framework should call when an I/O request completes.
old-location: wdf\iwdfiorequest_setcompletioncallback.htm
tech.root: wdf
ms.assetid: 316b8b75-91ca-4866-b66d-3f66f20126df
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::SetCompletionCallback"]
ms.keywords: IWDFIoRequest interface,SetCompletionCallback method, IWDFIoRequest.SetCompletionCallback, IWDFIoRequest::SetCompletionCallback, SetCompletionCallback, SetCompletionCallback method, SetCompletionCallback method,IWDFIoRequest interface, UMDFRequestObjectRef_81bdbb22-6221-472d-b2de-a1cc0b9b0c11.xml, umdf.iwdfiorequest_setcompletioncallback, wdf.iwdfiorequest_setcompletioncallback, wudfddi/IWDFIoRequest::SetCompletionCallback
f1_keywords:
 - "wudfddi/IWDFIoRequest.SetCompletionCallback"
 - "IWDFIoRequest.SetCompletionCallback"
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
- IWDFIoRequest.SetCompletionCallback
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::SetCompletionCallback


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetCompletionCallback</b> method registers the interface for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">OnCompletion</a> method that the framework should call when an I/O request completes.


## -parameters




### -param pCompletionCallback [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackrequestcompletion">IRequestCallbackRequestCompletion</a> interface whose <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">OnCompletion</a> method the framework calls after the I/O request completes. Beginning with version 1.9 of UMDF, the driver can specify <b>NULL</b> to deregister a previously registered <b>OnCompletion</b> method.


### -param pContext [in, optional]

A pointer to a buffer that contains context information that is related to the request completion. The framework passes this context information in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">IRequestCallbackRequestCompletion::OnCompletion</a> method. This parameter is optional and can be <b>NULL</b>.


## -remarks



If a driver that forwards an I/O request requires notification when the lower-level driver completes the request, the driver can provide a completion routine and call <b>SetCompletionCallback</b> to register the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackrequestcompletion">IRequestCallbackRequestCompletion</a> interface for the completion routine. The framework calls the completion routine after the lower-level driver completes the I/O request.


#### Examples

For a code example of how to use the <b>SetCompletionCallback</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackrequestcompletion">IRequestCallbackRequestCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackrequestcompletion-oncompletion">IRequestCallbackRequestCompletion::OnCompletion</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>
 

 

