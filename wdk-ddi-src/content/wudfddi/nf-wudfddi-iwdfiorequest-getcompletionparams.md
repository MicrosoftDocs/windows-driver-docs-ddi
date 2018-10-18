---
UID: NF:wudfddi.IWDFIoRequest.GetCompletionParams
title: IWDFIoRequest::GetCompletionParams
author: windows-driver-content
description: The GetCompletionParams method retrieves the parameters object for the completion of an I/O request object.
old-location: wdf\iwdfiorequest_getcompletionparams.htm
tech.root: wdf
ms.assetid: aaca14ff-9ea2-43f4-bfa9-9151d855c3af
ms.date: 2/26/2018
ms.keywords: GetCompletionParams, GetCompletionParams method, GetCompletionParams method,IWDFIoRequest interface, IWDFIoRequest interface,GetCompletionParams method, IWDFIoRequest.GetCompletionParams, IWDFIoRequest::GetCompletionParams, UMDFRequestObjectRef_dbfb5f9c-c1ad-425d-9bcb-627cc961d00d.xml, umdf.iwdfiorequest_getcompletionparams, wdf.iwdfiorequest_getcompletionparams, wudfddi/IWDFIoRequest::GetCompletionParams
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
-	IWDFIoRequest.GetCompletionParams
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetCompletionParams


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletionParams</b> method retrieves the parameters object for the completion of an I/O request object.


## -parameters




### -param ppCompletionParams [out]

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a> interface.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a>
 

 

