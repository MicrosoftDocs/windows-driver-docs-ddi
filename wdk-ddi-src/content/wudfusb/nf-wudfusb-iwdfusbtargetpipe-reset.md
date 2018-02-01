---
UID: NF:wudfusb.IWDFUsbTargetPipe.Reset
title: IWDFUsbTargetPipe::Reset method
author: windows-driver-content
description: The Reset method resets the data toggle and clears the stall condition on a USB pipe.
old-location: wdf\iwdfusbtargetpipe_reset.htm
old-project: wdf
ms.assetid: 8d42dd60-a032-4486-87e0-2204e833035b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfusbtargetpipe_reset, Reset method, Reset method, IWDFUsbTargetPipe interface, IWDFUsbTargetPipe, Reset, IWDFUsbTargetPipe interface, Reset method, wudfusb/IWDFUsbTargetPipe::Reset, UMDFUSBref_510f6831-e75f-41b6-9637-7400fe89e4d3.xml, umdf.iwdfusbtargetpipe_reset, IWDFUsbTargetPipe::Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfusb.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUsbTargetPipe.Reset
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::Reset method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reset</b> method resets the data toggle and clears the stall condition on a USB pipe.


## -syntax


````
HRESULT  Reset();
````


## -parameters





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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn926942">Reset</a> successfully reset the data toggle and cleared the stall condition. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn926942">Reset</a> encountered an allocation failure.

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

For more information about how <b>Reset</b> works, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540300">WinUsb_ResetPipe</a> function.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540300">WinUsb_ResetPipe</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::Reset method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

