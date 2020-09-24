---
UID: NF:wudfddi.IWDFIoRequest.CancelSentRequest
title: IWDFIoRequest::CancelSentRequest (wudfddi.h)
description: The CancelSentRequest method attempts to cancel the I/O request that the driver previously submitted to an I/O target.
old-location: wdf\iwdfiorequest_cancelsentrequest.htm
tech.root: wdf
ms.assetid: 1951a2e8-c2f0-42bc-9deb-8d2a049817c4
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::CancelSentRequest"]
ms.keywords: CancelSentRequest, CancelSentRequest method, CancelSentRequest method,IWDFIoRequest interface, IWDFIoRequest interface,CancelSentRequest method, IWDFIoRequest.CancelSentRequest, IWDFIoRequest::CancelSentRequest, UMDFRequestObjectRef_cf439791-044b-4cd8-8a1c-eafc7b266897.xml, umdf.iwdfiorequest_cancelsentrequest, wdf.iwdfiorequest_cancelsentrequest, wudfddi/IWDFIoRequest::CancelSentRequest
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
 - IWDFIoRequest::CancelSentRequest
 - wudfddi/IWDFIoRequest::CancelSentRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest.CancelSentRequest
---

# IWDFIoRequest::CancelSentRequest


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CancelSentRequest</b> method attempts to cancel the I/O request that the driver previously submitted to an I/O target.

## -returns

<b>CancelSentRequest</b> returns a BOOL value that indicates whether the cancel request was successfully delivered to the request's owner. <b>TRUE</b> indicates the request was successfully delivered. <b>FALSE</b> indicates the request was not successfully delivered.

## -remarks

A driver can call <b>CancelSentRequest</b> to attempt to cancel the I/O request that it previously sent to an I/O target by calling the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> method.

If the request is in the I/O target's queue, the framework cancels the request. If the framework already delivered the request to the I/O target's driver, and if that driver previously called <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> to enabling canceling, the framework calls that driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method. If the target's driver did not call <b>IWDFIoRequest::MarkCancelable</b>, the request is not canceled unless the request subsequently becomes cancelable.

If the driver previously registered the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackrequestcompletion">IRequestCallbackRequestCompletion</a> interface for the request's completion routine, the framework calls the completion routine after the request is canceled.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackrequestcompletion">IRequestCallbackRequestCompletion</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>