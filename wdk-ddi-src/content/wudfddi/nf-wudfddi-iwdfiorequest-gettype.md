---
UID: NF:wudfddi.IWDFIoRequest.GetType
title: IWDFIoRequest::GetType (wudfddi.h)
description: The GetType method retrieves the type of operation that a request contains.
old-location: wdf\iwdfiorequest_gettype.htm
tech.root: wdf
ms.assetid: 3be2ef6c-391e-4d1c-a1a6-e3228f5cc67d
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::GetType"]
ms.keywords: GetType, GetType method, GetType method,IWDFIoRequest interface, IWDFIoRequest interface,GetType method, IWDFIoRequest.GetType, IWDFIoRequest::GetType, UMDFRequestObjectRef_8f8bc7b0-b527-4325-a2dc-a9ef5e73cc28.xml, umdf.iwdfiorequest_gettype, wdf.iwdfiorequest_gettype, wudfddi/IWDFIoRequest::GetType
f1_keywords:
 - "wudfddi/IWDFIoRequest.GetType"
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
- IWDFIoRequest.GetType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetType


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetType</b> method retrieves the type of operation that a request contains.


## -returns



<b>GetType</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>-typed value that identifies the request type and why the request is sent to the driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>
 

 

