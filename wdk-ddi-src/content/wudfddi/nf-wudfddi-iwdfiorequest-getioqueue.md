---
UID: NF:wudfddi.IWDFIoRequest.GetIoQueue
title: IWDFIoRequest::GetIoQueue (wudfddi.h)
description: The GetIoQueue method retrieves the I/O queue object that is associated with an I/O request.
old-location: wdf\iwdfiorequest_getioqueue.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::GetIoQueue"]
ms.keywords: GetIoQueue, GetIoQueue method, GetIoQueue method,IWDFIoRequest interface, IWDFIoRequest interface,GetIoQueue method, IWDFIoRequest.GetIoQueue, IWDFIoRequest::GetIoQueue, UMDFRequestObjectRef_1e603d95-06ae-45a8-ab4d-3592d6e140bf.xml, umdf.iwdfiorequest_getioqueue, wdf.iwdfiorequest_getioqueue, wudfddi/IWDFIoRequest::GetIoQueue
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
 - IWDFIoRequest::GetIoQueue
 - wudfddi/IWDFIoRequest::GetIoQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest::GetIoQueue
---

# IWDFIoRequest::GetIoQueue


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetIoQueue</b> method retrieves the I/O queue object that is associated with an I/O request.

## -parameters

### -param ppWdfIoQueue [out]


A pointer to a variable that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that the I/O request is associated with.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>

