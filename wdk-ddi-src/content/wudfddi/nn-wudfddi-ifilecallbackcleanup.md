---
UID: NN:wudfddi.IFileCallbackCleanup
title: IFileCallbackCleanup (wudfddi.h)
description: The framework can notify a driver when the driver should perform a cleanup operation.
old-location: wdf\ifilecallbackcleanup.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IFileCallbackCleanup interface"]
ms.keywords: IFileCallbackCleanup, IFileCallbackCleanup interface, IFileCallbackCleanup interface,described, UMDFFileObjectRef_8f409e94-4586-4f25-a8ba-1c39544ec661.xml, umdf.ifilecallbackcleanup, wdf.ifilecallbackcleanup, wudfddi/IFileCallbackCleanup
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
 - IFileCallbackCleanup
 - wudfddi/IFileCallbackCleanup
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IFileCallbackCleanup
---

# IFileCallbackCleanup interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The framework can notify a driver when the driver should perform a cleanup operation.  The framework notifies the driver in response to an application calling the <b>CloseHandle</b> Microsoft Win32 function. The driver can handle the notification by registering the <b>IFileCallbackCleanup</b> interface.

A driver registers the <b>IFileCallbackCleanup</b> interface when it calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFileCallbackCleanup</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IFileCallbackCleanup</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
