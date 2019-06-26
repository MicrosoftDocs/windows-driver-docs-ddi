---
UID: NN:wudfusb.IWDFUsbTargetPipe2
title: IWDFUsbTargetPipe2 (wudfusb.h)
description: The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.
old-location: wdf\iwdfusbtargetpipe2.htm
tech.root: wdf
ms.assetid: c3df39cb-17f4-4f68-bde3-f53ba40dde85
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetPipe2, IWDFUsbTargetPipe2 interface, IWDFUsbTargetPipe2 interface,described, UMDFUSBref_835fc9c8-f01e-4b39-ab06-530f36886ea3.xml, umdf.iwdfusbtargetpipe2, wdf.iwdfusbtargetpipe2, wudfusb/IWDFUsbTargetPipe2
ms.topic: interface
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUsbTargetPipe2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The IWDFUsbTargetPipe2 interface exposes a USB pipe (endpoint), which is also an I/O target.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetPipe2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>. <b>IWDFUsbTargetPipe2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUsbTargetPipe2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">IWDFUsbTargetPipe2::ConfigureContinuousReader</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe2-configurecontinuousreader">ConfigureContinuousReader</a> method configures the framework to continuously read from a USB pipe.

</td>
</tr>
</table> 


## -remarks



Drivers obtain the <b>IWDFUsbTargetPipe2</b> interface by calling <b>IWDFUsbTargetPipe::QueryInterface</b>.



