---
UID: NF:wudfddi.IWDFIoRequest.IsFrom32BitProcess
title: IWDFIoRequest::IsFrom32BitProcess (wudfddi.h)
description: The IsFrom32BitProcess method determines whether a request originated from a 32-bit process.
old-location: wdf\iwdfiorequest_isfrom32bitprocess.htm
tech.root: wdf
ms.assetid: 80e43bd7-9ab9-46b0-a7f3-08c3577be4bc
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::IsFrom32BitProcess"]
ms.keywords: IWDFIoRequest interface,IsFrom32BitProcess method, IWDFIoRequest.IsFrom32BitProcess, IWDFIoRequest::IsFrom32BitProcess, IsFrom32BitProcess, IsFrom32BitProcess method, IsFrom32BitProcess method,IWDFIoRequest interface, UMDFRequestObjectRef_728bc611-2c40-4a49-b967-77e388072860.xml, umdf.iwdfiorequest_isfrom32bitprocess, wdf.iwdfiorequest_isfrom32bitprocess, wudfddi/IWDFIoRequest::IsFrom32BitProcess
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
 - IWDFIoRequest::IsFrom32BitProcess
 - wudfddi/IWDFIoRequest::IsFrom32BitProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest.IsFrom32BitProcess
---

# IWDFIoRequest::IsFrom32BitProcess


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsFrom32BitProcess</b> method determines whether a request originated from a 32-bit process.

## -returns

<b>IsFrom32BitProcess</b> returns a BOOL value that indicates whether the request originated from a 32-bit process. <b>TRUE</b> indicates the request originated from a 32-bit process. <b>FALSE</b> indicates the request did not originate from a 32-bit process.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>

