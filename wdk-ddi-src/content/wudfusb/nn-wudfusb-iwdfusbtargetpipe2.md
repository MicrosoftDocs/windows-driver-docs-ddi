---
UID: NN:wudfusb.IWDFUsbTargetPipe2
title: IWDFUsbTargetPipe2 (wudfusb.h)
description: The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.
old-location: wdf\iwdfusbtargetpipe2.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe2 interface"]
ms.keywords: IWDFUsbTargetPipe2, IWDFUsbTargetPipe2 interface, IWDFUsbTargetPipe2 interface,described, UMDFUSBref_835fc9c8-f01e-4b39-ab06-530f36886ea3.xml, umdf.iwdfusbtargetpipe2, wdf.iwdfusbtargetpipe2, wudfusb/IWDFUsbTargetPipe2
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
 - IWDFUsbTargetPipe2
 - wudfusb/IWDFUsbTargetPipe2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetPipe2
---

# IWDFUsbTargetPipe2 interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetPipe2</b> interface inherits from <a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>. <b>IWDFUsbTargetPipe2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

Drivers obtain the <b>IWDFUsbTargetPipe2</b> interface by calling <b>IWDFUsbTargetPipe::QueryInterface</b>.
