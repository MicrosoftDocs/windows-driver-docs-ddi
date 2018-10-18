---
UID: NF:wudfddi.IWDFIoRequest.CompleteWithInformation
title: IWDFIoRequest::CompleteWithInformation
author: windows-driver-content
description: The CompleteWithInformation method completes a request with the supplied information.
old-location: wdf\iwdfiorequest_completewithinformation.htm
tech.root: wdf
ms.assetid: 43089473-3255-4016-8d51-f5ad4261bd8d
ms.date: 02/26/2018
ms.keywords: CompleteWithInformation, CompleteWithInformation method, CompleteWithInformation method,IWDFIoRequest interface, IWDFIoRequest interface,CompleteWithInformation method, IWDFIoRequest.CompleteWithInformation, IWDFIoRequest::CompleteWithInformation, UMDFRequestObjectRef_c01f0d7b-3b4d-442c-8425-a99c064609ee.xml, umdf.iwdfiorequest_completewithinformation, wdf.iwdfiorequest_completewithinformation, wudfddi/IWDFIoRequest::CompleteWithInformation
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
-	IWDFIoRequest.CompleteWithInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::CompleteWithInformation


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CompleteWithInformation</b> method completes a request with the supplied information.


## -parameters




### -param CompletionStatus [in]

A status value to complete the request with. 


### -param Information [in]

Additional driver-supplied information that is related to the I/O operation.

For read, write, and device I/O control operations, the driver should supply the number of bytes that are transferred.


## -returns



None




## -remarks



For more information about completing an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

For a code example of how to use the <b>CompleteWithInformation</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>
 

 

