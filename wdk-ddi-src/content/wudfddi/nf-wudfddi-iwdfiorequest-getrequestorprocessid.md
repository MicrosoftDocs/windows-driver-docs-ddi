---
UID: NF:wudfddi.IWDFIoRequest.GetRequestorProcessId
title: IWDFIoRequest::GetRequestorProcessId (wudfddi.h)
description: The GetRequestorProcessId method retrieves the identifier of the process that sent an I/O request.
old-location: wdf\iwdfiorequest_getrequestorprocessid.htm
tech.root: wdf
ms.assetid: 8bad169a-3a89-460d-9e6e-e8c1994970a8
ms.date: 02/26/2018
ms.keywords: GetRequestorProcessId, GetRequestorProcessId method, GetRequestorProcessId method,IWDFIoRequest interface, IWDFIoRequest interface,GetRequestorProcessId method, IWDFIoRequest.GetRequestorProcessId, IWDFIoRequest::GetRequestorProcessId, UMDFRequestObjectRef_9464f328-c7a7-4126-896c-69bc4ab0b5ba.xml, umdf.iwdfiorequest_getrequestorprocessid, wdf.iwdfiorequest_getrequestorprocessid, wudfddi/IWDFIoRequest::GetRequestorProcessId
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest.GetRequestorProcessId"
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
- IWDFIoRequest.GetRequestorProcessId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetRequestorProcessId


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRequestorProcessId</b> method retrieves the identifier of the process that sent an I/O request.


## -parameters






## -returns



<b>GetRequestorProcessId</b> returns the identifier of the process that sent the I/O request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>
 

 

