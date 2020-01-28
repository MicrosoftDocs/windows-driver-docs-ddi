---
UID: NN:wudfddi.IWDFRequestCompletionParams
title: IWDFRequestCompletionParams (wudfddi.h)
description: The IWDFRequestCompletionParams interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or an asynchronous I/O operation completes.
old-location: wdf\iwdfrequestcompletionparams.htm
tech.root: wdf
ms.assetid: f297c6e0-927a-4fb3-bab4-00fdd610a684
ms.date: 02/26/2018
ms.keywords: IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, IWDFRequestCompletionParams interface,described, UMDFRequestObjectRef_746528f7-b23f-4907-8661-e228fa99df1c.xml, umdf.iwdfrequestcompletionparams, wdf.iwdfrequestcompletionparams, wudfddi/IWDFRequestCompletionParams
f1_keywords:
 - "wudfddi/IWDFRequestCompletionParams"
req.header: wudfddi.h
req.include-header: 
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
- IWDFRequestCompletionParams
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRequestCompletionParams interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFRequestCompletionParams</b> interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or an asynchronous I/O operation completes.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFRequestCompletionParams</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFRequestCompletionParams</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

