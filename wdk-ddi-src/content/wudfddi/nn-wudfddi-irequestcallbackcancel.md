---
UID: NN:wudfddi.IRequestCallbackCancel
title: IRequestCallbackCancel (wudfddi.h)
description: A driver is notified when an I/O request that the driver is currently processing is to be canceled.
old-location: wdf\irequestcallbackcancel.htm
tech.root: wdf
ms.assetid: d6aec38c-6cbb-494c-9fa4-10b6f4a30ae0
ms.date: 02/26/2018
keywords: ["IRequestCallbackCancel interface"]
ms.keywords: IRequestCallbackCancel, IRequestCallbackCancel interface, IRequestCallbackCancel interface,described, UMDFRequestObjectRef_6f54b76d-812d-437c-8c02-7d9e3e177b90.xml, umdf.irequestcallbackcancel, wdf.irequestcallbackcancel, wudfddi/IRequestCallbackCancel
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
 - IRequestCallbackCancel
 - wudfddi/IRequestCallbackCancel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wudfddi.h
api_name:
 - IRequestCallbackCancel
---

# IRequestCallbackCancel interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver is notified when an I/O request that the driver is currently processing is to be canceled. The driver is notified when an application calls the Microsoft Win32 <b>CancelIo</b>, <b>CancelIoEx</b>, or <b>CancelSynchronousIo</b> function. The driver can handle the notification by registering the <b>IRequestCallbackCancel</b> interface.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRequestCallbackCancel</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IRequestCallbackCancel</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

A driver registers the <b>IRequestCallbackCancel</b> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-markcancelable">IWDFIoRequest::MarkCancelable</a> method to enable the canceling of an I/O request. For more information about how to cancel I/O requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

