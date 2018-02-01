---
UID: NF:wudfddi.IWDFIoRequest.SetCompletionCallback
title: IWDFIoRequest::SetCompletionCallback method
author: windows-driver-content
description: The SetCompletionCallback method registers the interface for the OnCompletion method that the framework should call when an I/O request completes.
old-location: wdf\iwdfiorequest_setcompletioncallback.htm
old-project: wdf
ms.assetid: 316b8b75-91ca-4866-b66d-3f66f20126df
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfiorequest_setcompletioncallback, SetCompletionCallback method, IWDFIoRequest interface, SetCompletionCallback method, IWDFIoRequest::SetCompletionCallback, wudfddi/IWDFIoRequest::SetCompletionCallback, UMDFRequestObjectRef_81bdbb22-6221-472d-b2de-a1cc0b9b0c11.xml, SetCompletionCallback, IWDFIoRequest interface, SetCompletionCallback method, IWDFIoRequest, umdf.iwdfiorequest_setcompletioncallback
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
-	IWDFIoRequest.SetCompletionCallback
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::SetCompletionCallback method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetCompletionCallback</b> method registers the interface for the <a href="https://msdn.microsoft.com/1a4787da-2813-4a7a-820a-5c078175aba5">OnCompletion</a> method that the framework should call when an I/O request completes.


## -syntax


````
void SetCompletionCallback(
  [in]           IRequestCallbackRequestCompletion *pCompletionCallback,
  [in, optional] void                              *pContext
);
````


## -parameters




### -param pCompletionCallback [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a> interface whose <a href="https://msdn.microsoft.com/1a4787da-2813-4a7a-820a-5c078175aba5">OnCompletion</a> method the framework calls after the I/O request completes. Beginning with version 1.9 of UMDF, the driver can specify <b>NULL</b> to deregister a previously registered <b>OnCompletion</b> method.


### -param pContext [in, optional]

A pointer to a buffer that contains context information that is related to the request completion. The framework passes this context information in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> method. This parameter is optional and can be <b>NULL</b>.


## -returns


None



## -remarks


If a driver that forwards an I/O request requires notification when the lower-level driver completes the request, the driver can provide a completion routine and call <b>SetCompletionCallback</b> to register the <a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a> interface for the completion routine. The framework calls the completion routine after the lower-level driver completes the I/O request.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="..\wudfddi\nn-wudfddi-irequestcallbackrequestcompletion.md">IRequestCallbackRequestCompletion</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::SetCompletionCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

