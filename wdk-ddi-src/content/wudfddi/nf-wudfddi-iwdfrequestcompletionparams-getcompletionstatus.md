---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetCompletionStatus
title: IWDFRequestCompletionParams::GetCompletionStatus (wudfddi.h)
description: The GetCompletionStatus method retrieves the completion status of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getcompletionstatus.htm
tech.root: wdf
ms.assetid: 8959fc25-2477-485a-aa40-10d6228cb476
ms.date: 02/26/2018
keywords: ["IWDFRequestCompletionParams::GetCompletionStatus"]
ms.keywords: GetCompletionStatus, GetCompletionStatus method, GetCompletionStatus method,IWDFRequestCompletionParams interface, IWDFRequestCompletionParams interface,GetCompletionStatus method, IWDFRequestCompletionParams.GetCompletionStatus, IWDFRequestCompletionParams::GetCompletionStatus, UMDFRequestObjectRef_b3664f4d-fdb1-425f-be0a-3b4150762b9d.xml, umdf.iwdfrequestcompletionparams_getcompletionstatus, wdf.iwdfrequestcompletionparams_getcompletionstatus, wudfddi/IWDFRequestCompletionParams::GetCompletionStatus
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
 - IWDFRequestCompletionParams::GetCompletionStatus
 - wudfddi/IWDFRequestCompletionParams::GetCompletionStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRequestCompletionParams.GetCompletionStatus
---

# IWDFRequestCompletionParams::GetCompletionStatus


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletionStatus</b> method retrieves the completion status of an I/O request.

## -returns

<b>GetCompletionStatus</b> returns S_OK for a successful completion status. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfrequestcompletionparams">IWDFRequestCompletionParams</a>

