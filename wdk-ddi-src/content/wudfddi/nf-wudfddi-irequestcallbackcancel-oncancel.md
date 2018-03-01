---
UID: NF:wudfddi.IRequestCallbackCancel.OnCancel
title: IRequestCallbackCancel::OnCancel method
author: windows-driver-content
description: The OnCancel method is called when an application cancels an I/O operation through the Microsoft Win32 CancelIo, CancelIoEx, or CancelSynchronousIo function.
old-location: wdf\irequestcallbackcancel_oncancel.htm
old-project: wdf
ms.assetid: 67c85eaa-bb47-4384-8e37-fdbbc879b352
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IRequestCallbackCancel, IRequestCallbackCancel interface, OnCancel method, IRequestCallbackCancel::OnCancel, OnCancel method, OnCancel method, IRequestCallbackCancel interface, OnCancel,IRequestCallbackCancel.OnCancel, UMDFRequestObjectRef_bdb47237-28bf-4b07-9bcb-f8d029636d2d.xml, umdf.irequestcallbackcancel_oncancel, wdf.irequestcallbackcancel_oncancel, wudfddi/IRequestCallbackCancel::OnCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IRequestCallbackCancel.OnCancel
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IRequestCallbackCancel::OnCancel method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCancel</b> method is called when an application cancels an I/O operation through the Microsoft Win32 <b>CancelIo</b>, <b>CancelIoEx</b>, or <b>CancelSynchronousIo</b> function. 


## -syntax


````
void OnCancel(
  [in] IWDFIoRequest *pWdfRequest
);
````


## -parameters




### -param pWdfRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object to cancel. 


## -returns



None




## -remarks



The framework calls the <b>OnCancel</b> method to cancel the I/O request that the <i>pWdfRequest</i> parameter identifies. The driver should first determine whether it can cancel the I/O request. If the request can be canceled, the driver should cancel it. For more information about how to cancel a request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

If the driver cancels the request, the driver must also complete the request by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> method with the <i>CompletionStatus</i> parameter set to HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED). 

The framework does not call <b>OnCancel</b> to cancel a request unless the driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> method to enable cancellation of the request and to register the <a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a> interface.

The User-Mode Driver Framework (UMDF) allows only one <b>OnCancel</b> method per queue. Therefore, when a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> for requests that are associated with a particular queue to enable the framework to cancel those requests, the driver must pass a pointer to the <a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a> interface for the same request-callback object. Later, to cancel each request, the framework passes a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request in a call to this request-callback object's <b>OnCancel</b> method.




## -see-also

<a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRequestCallbackCancel::OnCancel method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

