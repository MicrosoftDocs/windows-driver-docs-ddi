---
UID: NN:wudfusb.IWDFUsbRequestCompletionParams
title: IWDFUsbRequestCompletionParams (wudfusb.h)
description: The IWDFUsbRequestCompletionParams interface exposes the parameters object for the completion of a USB request object. The parameters object is primarily required for asynchronous I/O and layered drivers.
old-location: wdf\iwdfusbrequestcompletionparams.htm
tech.root: wdf
ms.assetid: 50a0c8c9-06c6-48c9-a799-0949cf415f6e
ms.date: 02/26/2018
ms.keywords: IWDFUsbRequestCompletionParams, IWDFUsbRequestCompletionParams interface, IWDFUsbRequestCompletionParams interface,described, UMDFRequestObjectRef_f55ce370-f488-405f-a104-9a85fcab6cbb.xml, umdf.iwdfusbrequestcompletionparams, wdf.iwdfusbrequestcompletionparams, wudfusb/IWDFUsbRequestCompletionParams
ms.topic: interface
f1_keywords:
 - "wudfusb/IWDFUsbRequestCompletionParams"
req.header: wudfusb.h
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
- IWDFUsbRequestCompletionParams
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbRequestCompletionParams interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUsbRequestCompletionParams</b> interface exposes the parameters object for the completion of a USB request object. The parameters object is primarily required for asynchronous I/O and layered drivers.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbRequestCompletionParams</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfrequestcompletionparams">IWDFRequestCompletionParams</a>. <b>IWDFUsbRequestCompletionParams</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUsbRequestCompletionParams</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getcompletedusbrequesttype">IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getcompletedusbrequesttype">GetCompletedUsbRequestType</a> method retrieves the type of operation that the request to be completed contains.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getdevicecontroltransferparameters">IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getdevicecontroltransferparameters">GetDeviceControlTransferParameters</a> method retrieves parameters that are associated with the completion of a device I/O control request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getpipereadparameters">IWDFUsbRequestCompletionParams::GetPipeReadParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getpipereadparameters">GetPipeReadParameters</a> method retrieves parameters that are associated with the completion of a read request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getpipewriteparameters">IWDFUsbRequestCompletionParams::GetPipeWriteParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbrequestcompletionparams-getpipewriteparameters">GetPipeWriteParameters</a> method retrieves parameters that are associated with the completion of a write request.

</td>
</tr>
</table> 

