---
UID: NN:wudfddi.IImpersonateCallback
title: IImpersonateCallback (wudfddi.h)
description: The IImpersonateCallback interface contains a method that handles impersonation.
old-location: wdf\iimpersonatecallback.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IImpersonateCallback interface"]
ms.keywords: IImpersonateCallback, IImpersonateCallback interface, IImpersonateCallback interface,described, UMDFRequestObjectRef_a92c4df0-b16b-4fc0-b858-4b2cdd59c3b2.xml, umdf.iimpersonatecallback, wdf.iimpersonatecallback, wudfddi/IImpersonateCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IImpersonateCallback
 - wudfddi/IImpersonateCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wudfddi.h
api_name:
 - IImpersonateCallback
---

# IImpersonateCallback interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IImpersonateCallback</b> interface contains a method that handles impersonation.

A driver registers the <b>IImpersonateCallback</b> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-impersonate">IWDFIoRequest::Impersonate</a> method.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IImpersonateCallback</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IImpersonateCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
