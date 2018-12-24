---
UID: NF:wudfusb.IWDFUsbTargetPipe.IsInEndPoint
title: IWDFUsbTargetPipe::IsInEndPoint
description: The IsInEndPoint method determines whether a USB pipe (endpoint) is an IN pipe.
old-location: wdf\iwdfusbtargetpipe_isinendpoint.htm
tech.root: wdf
ms.assetid: c1cba1fa-3952-4f2f-829f-2f5983349df8
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetPipe interface,IsInEndPoint method, IWDFUsbTargetPipe.IsInEndPoint, IWDFUsbTargetPipe::IsInEndPoint, IsInEndPoint, IsInEndPoint method, IsInEndPoint method,IWDFUsbTargetPipe interface, UMDFUSBref_07580c26-1173-4624-9199-c8dc8ef59edf.xml, umdf.iwdfusbtargetpipe_isinendpoint, wdf.iwdfusbtargetpipe_isinendpoint, wudfusb/IWDFUsbTargetPipe::IsInEndPoint
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetPipe.IsInEndPoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe::IsInEndPoint


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsInEndPoint</b> method determines whether a USB pipe (endpoint) is an IN pipe.


## -parameters






## -returns



<b>IsInEndPoint</b> returns a BOOL value that indicates whether the USB pipe is an IN pipe. <b>TRUE</b> indicates the pipe is an IN pipe. <b>FALSE</b> indicates the pipe is not an IN pipe.




## -remarks



If the USB pipe is an IN pipe, a UMDF driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a> method to format a read request. The framework can then send the request to the USB pipe.

<div class="alert"><b>Note</b>    The meaning of IN and OUT is opposite in WDF and USB.</div>
<div> </div>

#### Examples

For a code example of how to use the <b>IsInEndPoint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>
 

 

