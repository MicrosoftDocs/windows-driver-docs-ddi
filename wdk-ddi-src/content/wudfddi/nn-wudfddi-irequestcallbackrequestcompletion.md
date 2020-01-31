---
UID: NN:wudfddi.IRequestCallbackRequestCompletion
title: IRequestCallbackRequestCompletion (wudfddi.h)
description: A driver implements the IRequestCallbackRequestCompletion interface to complete a request object.
old-location: wdf\irequestcallbackrequestcompletion.htm
tech.root: wdf
ms.assetid: 65803145-8043-4902-981a-9dbbda2d69e9
ms.date: 02/26/2018
ms.keywords: IRequestCallbackRequestCompletion, IRequestCallbackRequestCompletion interface, IRequestCallbackRequestCompletion interface,described, UMDFRequestObjectRef_9940e95b-e321-4cdf-95bb-3540e95f6094.xml, umdf.irequestcallbackrequestcompletion, wdf.irequestcallbackrequestcompletion, wudfddi/IRequestCallbackRequestCompletion
f1_keywords:
 - "wudfddi/IRequestCallbackRequestCompletion"
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wudfddi.h
api_name:
- IRequestCallbackRequestCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRequestCallbackRequestCompletion interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver implements the <b>IRequestCallbackRequestCompletion</b> interface to complete a request object. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRequestCallbackRequestCompletion</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IRequestCallbackRequestCompletion</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



A driver registers the <b>IRequestCallbackRequestCompletion</b> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-setcompletioncallback">IWDFIoRequest::SetCompletionCallback</a> method. For more information about how a driver completes an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.



