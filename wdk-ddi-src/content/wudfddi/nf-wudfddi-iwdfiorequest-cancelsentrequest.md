---
UID: NF:wudfddi.IWDFIoRequest.CancelSentRequest
title: IWDFIoRequest::CancelSentRequest method
author: windows-driver-content
description: The CancelSentRequest method attempts to cancel the I/O request that the driver previously submitted to an I/O target.
old-location: wdf\iwdfiorequest_cancelsentrequest.htm
old-project: wdf
ms.assetid: 1951a2e8-c2f0-42bc-9deb-8d2a049817c4
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: CancelSentRequest method, CancelSentRequest method, IWDFIoRequest interface, CancelSentRequest,IWDFIoRequest.CancelSentRequest, IWDFIoRequest, IWDFIoRequest interface, CancelSentRequest method, IWDFIoRequest::CancelSentRequest, UMDFRequestObjectRef_cf439791-044b-4cd8-8a1c-eafc7b266897.xml, umdf.iwdfiorequest_cancelsentrequest, wdf.iwdfiorequest_cancelsentrequest, wudfddi/IWDFIoRequest::CancelSentRequest
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest.CancelSentRequest
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::CancelSentRequest method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CancelSentRequest</b> method attempts to cancel the I/O request that the driver previously submitted to an I/O target.


## -syntax


````
BOOL  CancelSentRequest();
````


## -parameters






## -returns



<b>CancelSentRequest</b> returns a BOOL value that indicates whether the cancel request was successfully delivered to the request's owner. <b>TRUE</b> indicates the request was successfully delivered. <b>FALSE</b> indicates the request was not successfully delivered.




## -remarks



A driver can call <b>CancelSentRequest</b> to attempt to cancel the I/O request that it previously sent to an I/O target by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method.

If the request is in the I/O target's queue, the framework cancels the request. If the framework already delivered the request to the I/O target's driver, and if that driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> to enabling canceling, the framework calls that driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a> method. If the target's driver did not call <b>IWDFIoRequest::MarkCancelable</b>, the request is not canceled unless the request subsequently becomes cancelable.

If the driver previously registered the <a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a> interface for the request's completion routine, the framework calls the completion routine after the request is canceled.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::CancelSentRequest method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

