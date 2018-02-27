---
UID: NF:wudfddi.IWDFIoRequest.GetCompletionParams
title: IWDFIoRequest::GetCompletionParams method
author: windows-driver-content
description: The GetCompletionParams method retrieves the parameters object for the completion of an I/O request object.
old-location: wdf\iwdfiorequest_getcompletionparams.htm
old-project: wdf
ms.assetid: aaca14ff-9ea2-43f4-bfa9-9151d855c3af
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetCompletionParams method, GetCompletionParams method, IWDFIoRequest interface, GetCompletionParams,IWDFIoRequest.GetCompletionParams, IWDFIoRequest, IWDFIoRequest interface, GetCompletionParams method, IWDFIoRequest::GetCompletionParams, UMDFRequestObjectRef_dbfb5f9c-c1ad-425d-9bcb-627cc961d00d.xml, umdf.iwdfiorequest_getcompletionparams, wdf.iwdfiorequest_getcompletionparams, wudfddi/IWDFIoRequest::GetCompletionParams
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.GetCompletionParams
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetCompletionParams method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletionParams</b> method retrieves the parameters object for the completion of an I/O request object.


## -syntax


````
void GetCompletionParams(
  [out] IWDFRequestCompletionParams **ppCompletionParams
);
````


## -parameters




### -param ppCompletionParams [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a> interface.


## -returns



None




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="..\wudfddi\nn-wudfddi-iwdfrequestcompletionparams.md">IWDFRequestCompletionParams</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetCompletionParams method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

