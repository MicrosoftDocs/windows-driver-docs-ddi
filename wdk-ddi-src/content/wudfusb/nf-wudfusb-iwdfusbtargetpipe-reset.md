---
UID: NF:wudfusb.IWDFUsbTargetPipe.Reset
title: IWDFUsbTargetPipe::Reset (wudfusb.h)
description: The Reset method resets the data toggle and clears the stall condition on a USB pipe.
old-location: wdf\iwdfusbtargetpipe_reset.htm
tech.root: wdf
ms.assetid: 8d42dd60-a032-4486-87e0-2204e833035b
ms.date: 02/26/2018
keywords: ["IWDFUsbTargetPipe::Reset"]
ms.keywords: IWDFUsbTargetPipe interface,Reset method, IWDFUsbTargetPipe.Reset, IWDFUsbTargetPipe::Reset, Reset, Reset method, Reset method,IWDFUsbTargetPipe interface, UMDFUSBref_510f6831-e75f-41b6-9637-7400fe89e4d3.xml, umdf.iwdfusbtargetpipe_reset, wdf.iwdfusbtargetpipe_reset, wudfusb/IWDFUsbTargetPipe::Reset
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
 - IWDFUsbTargetPipe::Reset
 - wudfusb/IWDFUsbTargetPipe::Reset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbTargetPipe.Reset
---

# IWDFUsbTargetPipe::Reset


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reset</b> method resets the data toggle and clears the stall condition on a USB pipe.

## -returns

<b>Reset</b> returns one of the following values:

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

<a href="https://docs.microsoft.com/windows-hardware/test/wpt/reset">Reset</a> successfully reset the data toggle and cleared the stall condition. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/test/wpt/reset">Reset</a> encountered an allocation failure.

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

The <b>Reset</b> method generates a UMDF request and synchronously sends the request to the I/O target.

For more information about how <b>Reset</b> works, see the <a href="https://docs.microsoft.com/windows/win32/api/winusb/nf-winusb-winusb_resetpipe">WinUsb_ResetPipe</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetpipe">IWDFUsbTargetPipe</a>



<a href="https://docs.microsoft.com/windows/win32/api/winusb/nf-winusb-winusb_resetpipe">WinUsb_ResetPipe</a>

