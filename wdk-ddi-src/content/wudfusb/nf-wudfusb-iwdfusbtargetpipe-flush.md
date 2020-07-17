---
UID: NF:wudfusb.IWDFUsbTargetPipe.Flush
title: IWDFUsbTargetPipe::Flush (wudfusb.h)
description: The Flush method discards any data that WinUsb saved when the device returned more data than the client requested.
old-location: wdf\iwdfusbtargetpipe_flush.htm
tech.root: wdf
ms.assetid: d8e5cbf7-62c7-458d-a527-2508a8a5d066
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe::Flush"]
ms.keywords: Flush, Flush method, Flush method,IWDFUsbTargetPipe interface, IWDFUsbTargetPipe interface,Flush method, IWDFUsbTargetPipe.Flush, IWDFUsbTargetPipe::Flush, UMDFUSBref_5a569ab8-ccbd-47cc-93a6-8e61f366e6ee.xml, umdf.iwdfusbtargetpipe_flush, wdf.iwdfusbtargetpipe_flush, wudfusb/IWDFUsbTargetPipe::Flush
f1_keywords:
 - "wudfusb/IWDFUsbTargetPipe.Flush"
 - "IWDFUsbTargetPipe.Flush"
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
- IWDFUsbTargetPipe.Flush
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe::Flush


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Flush</b> method discards any data that WinUsb saved when the device returned more data than the client requested.


## -returns



<b>Flush</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> successfully discarded any extra data that WinUsb saved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>
 




## -remarks



The <b>Flush</b> method generates a UMDF request and synchronously sends the request to the I/O target.

For more information about how <b>Flush</b> works, see the <a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_flushpipe">WinUsb_FlushPipe</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_flushpipe">WinUsb_FlushPipe</a>
 

 

