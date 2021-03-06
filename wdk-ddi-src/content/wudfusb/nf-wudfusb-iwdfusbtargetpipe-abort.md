---
UID: NF:wudfusb.IWDFUsbTargetPipe.Abort
title: IWDFUsbTargetPipe::Abort (wudfusb.h)
description: The Abort method aborts all pending transfers on a USB pipe.
old-location: wdf\iwdfusbtargetpipe_abort.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe::Abort"]
ms.keywords: Abort, Abort method, Abort method,IWDFUsbTargetPipe interface, IWDFUsbTargetPipe interface,Abort method, IWDFUsbTargetPipe.Abort, IWDFUsbTargetPipe::Abort, UMDFUSBref_8b413047-741c-4d3c-a71e-d29a79e5226c.xml, umdf.iwdfusbtargetpipe_abort, wdf.iwdfusbtargetpipe_abort, wudfusb/IWDFUsbTargetPipe::Abort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFUsbTargetPipe::Abort
 - wudfusb/IWDFUsbTargetPipe::Abort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetPipe::Abort
---

# IWDFUsbTargetPipe::Abort


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Abort</b> method aborts all pending transfers on a USB pipe.

## -parameters

## -returns

<b>Abort</b> returns one of the following values:

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

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-abort">Abort</a> successfully aborted all pending transfers. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetpipe-abort">Abort</a> encountered an allocation failure.

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

The <b>Abort</b> method generates a UMDF request and synchronously sends the request to the I/O target.

For more information about how <b>Abort</b> works, see the <a href="/windows/win32/api/winusb/nf-winusb-winusb_abortpipe">WinUsb_AbortPipe</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>



<a href="/windows/win32/api/winusb/nf-winusb-winusb_abortpipe">WinUsb_AbortPipe</a>

