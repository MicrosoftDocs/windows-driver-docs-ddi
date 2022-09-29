---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetInformation
title: IWDFRequestCompletionParams::GetInformation (wudfddi.h)
description: The GetInformation method retrieves information that is associated with the completion of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getinformation.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFRequestCompletionParams::GetInformation"]
ms.keywords: GetInformation, GetInformation method, GetInformation method,IWDFRequestCompletionParams interface, IWDFRequestCompletionParams interface,GetInformation method, IWDFRequestCompletionParams.GetInformation, IWDFRequestCompletionParams::GetInformation, UMDFRequestObjectRef_f014a31c-ac37-419d-a318-31d910c646b1.xml, umdf.iwdfrequestcompletionparams_getinformation, wdf.iwdfrequestcompletionparams_getinformation, wudfddi/IWDFRequestCompletionParams::GetInformation
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
 - IWDFRequestCompletionParams::GetInformation
 - wudfddi/IWDFRequestCompletionParams::GetInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRequestCompletionParams::GetInformation
---

# IWDFRequestCompletionParams::GetInformation


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information that is associated with the completion of an I/O request.

## -returns

<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfrequestcompletionparams">IWDFRequestCompletionParams</a>

