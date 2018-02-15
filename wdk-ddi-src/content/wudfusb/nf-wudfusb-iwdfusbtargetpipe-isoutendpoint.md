---
UID: NF:wudfusb.IWDFUsbTargetPipe.IsOutEndPoint
title: IWDFUsbTargetPipe::IsOutEndPoint method
author: windows-driver-content
description: The IsOutEndPoint method determines whether a USB pipe (endpoint) is an OUT pipe.
old-location: wdf\iwdfusbtargetpipe_isoutendpoint.htm
old-project: wdf
ms.assetid: cb6c5b25-ea21-44cb-8b67-c5266c8bc1e4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IsOutEndPoint, wudfusb/IWDFUsbTargetPipe::IsOutEndPoint, IsOutEndPoint method, IsOutEndPoint method, IWDFUsbTargetPipe interface, wdf.iwdfusbtargetpipe_isoutendpoint, umdf.iwdfusbtargetpipe_isoutendpoint, IWDFUsbTargetPipe::IsOutEndPoint, IWDFUsbTargetPipe, UMDFUSBref_fc7a24f7-0bd6-4bb2-a9df-30d09e3b5e68.xml, IWDFUsbTargetPipe interface, IsOutEndPoint method
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
-	IWDFUsbTargetPipe.IsOutEndPoint
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::IsOutEndPoint method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsOutEndPoint</b> method determines whether a USB pipe (endpoint) is an OUT pipe.


## -syntax


````
BOOL  IsOutEndPoint();
````


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

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::IsOutEndPoint method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

