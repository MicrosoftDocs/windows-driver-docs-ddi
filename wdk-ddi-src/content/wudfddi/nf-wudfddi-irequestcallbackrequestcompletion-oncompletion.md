---
UID: NF:wudfddi.IRequestCallbackRequestCompletion.OnCompletion
title: IRequestCallbackRequestCompletion::OnCompletion
description: The OnCompletion method completes the specified request.
old-location: wdf\irequestcallbackrequestcompletion_oncompletion.htm
tech.root: wdf
ms.assetid: 1a4787da-2813-4a7a-820a-5c078175aba5
ms.date: 02/26/2018
ms.keywords: IRequestCallbackRequestCompletion interface,OnCompletion method, IRequestCallbackRequestCompletion.OnCompletion, IRequestCallbackRequestCompletion::OnCompletion, OnCompletion, OnCompletion method, OnCompletion method,IRequestCallbackRequestCompletion interface, UMDFRequestObjectRef_b3ec1892-f32f-4c52-80f6-8699a358ea8d.xml, umdf.irequestcallbackrequestcompletion_oncompletion, wdf.irequestcallbackrequestcompletion_oncompletion, wudfddi/IRequestCallbackRequestCompletion::OnCompletion
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
req.lib: 
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
-	IRequestCallbackRequestCompletion.OnCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRequestCallbackRequestCompletion::OnCompletion


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCompletion</b> method completes the specified request. 


## -parameters




### -param pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object. 


### -param pIoTarget [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a> interface for the I/O target object that represents the lower driver in the stack where the request was previously sent. 


### -param pParams [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a> interface for the parameters object for the completion request. 


### -param pContext [in]

A pointer to a buffer that contains context information that is related to the completion request.


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a> method. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a>
 

 

