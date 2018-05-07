---
UID: NF:wudfusb.IWDFUsbTargetPipe.IsOutEndPoint
title: IWDFUsbTargetPipe::IsOutEndPoint
author: windows-driver-content
description: The IsOutEndPoint method determines whether a USB pipe (endpoint) is an OUT pipe.
old-location: wdf\iwdfusbtargetpipe_isoutendpoint.htm
old-project: wdf
ms.assetid: cb6c5b25-ea21-44cb-8b67-c5266c8bc1e4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbTargetPipe interface,IsOutEndPoint method, IWDFUsbTargetPipe.IsOutEndPoint, IWDFUsbTargetPipe::IsOutEndPoint, IsOutEndPoint, IsOutEndPoint method, IsOutEndPoint method,IWDFUsbTargetPipe interface, UMDFUSBref_fc7a24f7-0bd6-4bb2-a9df-30d09e3b5e68.xml, umdf.iwdfusbtargetpipe_isoutendpoint, wdf.iwdfusbtargetpipe_isoutendpoint, wudfusb/IWDFUsbTargetPipe::IsOutEndPoint
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
-	IWDFUsbTargetPipe.IsOutEndPoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe::IsOutEndPoint


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsOutEndPoint</b> method determines whether a USB pipe (endpoint) is an OUT pipe.


## -parameters






## -returns



<b>IsOutEndPoint</b> returns a BOOL value that indicates whether the USB pipe is an OUT pipe. <b>TRUE</b> indicates the pipe is an OUT pipe. <b>FALSE</b> indicates the pipe is not an OUT pipe.




## -remarks



If the USB pipe is an OUT pipe, a UMDF driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a> method to format a write request. The framework can then send the request to the USB pipe.

<div class="alert"><b>Note</b>    The meaning of IN and OUT is opposite in WDF and USB.</div>
<div> </div>

#### Examples

For a code example of how to use the <b>IsOutEndPoint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>
 

 

