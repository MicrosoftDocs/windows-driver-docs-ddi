---
UID: NF:wudfddi.IWDFIoRequest.FormatUsingCurrentType
title: IWDFIoRequest::FormatUsingCurrentType (wudfddi.h)
description: The FormatUsingCurrentType method formats an I/O request so that the driver can forward it, unmodified, to the next-lower driver.
old-location: wdf\iwdfiorequest_formatusingcurrenttype.htm
tech.root: wdf
ms.assetid: 4cbf6d29-bccd-4629-b282-eb5314f9b4f4
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::FormatUsingCurrentType"]
ms.keywords: FormatUsingCurrentType, FormatUsingCurrentType method, FormatUsingCurrentType method,IWDFIoRequest interface, IWDFIoRequest interface,FormatUsingCurrentType method, IWDFIoRequest.FormatUsingCurrentType, IWDFIoRequest::FormatUsingCurrentType, UMDFRequestObjectRef_e16e60fe-557d-413c-a483-6bbe602986dc.xml, umdf.iwdfiorequest_formatusingcurrenttype, wdf.iwdfiorequest_formatusingcurrenttype, wudfddi/IWDFIoRequest::FormatUsingCurrentType
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
 - IWDFIoRequest::FormatUsingCurrentType
 - wudfddi/IWDFIoRequest::FormatUsingCurrentType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest.FormatUsingCurrentType
---

# IWDFIoRequest::FormatUsingCurrentType


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatUsingCurrentType</b> method formats an I/O request so that the driver can forward it, unmodified, to the next-lower driver.

## -remarks

When a driver receives an I/O request, the driver might forward the request to the local I/O target, unmodified. To forward the unmodified request, the driver must:

<ul>
<li>
Call <b>FormatUsingCurrentType</b> to format the request so that the framework can pass the request to the driver's local I/O target.

</li>
<li>
Call the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a> method to send the request to the I/O target.

</li>
</ul>

#### Examples

For a code example of how to use the <b>FormatUsingCurrentType</b> method, see <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-send">IWDFIoRequest::Send</a>