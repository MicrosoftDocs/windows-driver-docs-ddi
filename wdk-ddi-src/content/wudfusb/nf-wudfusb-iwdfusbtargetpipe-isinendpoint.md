---
UID: NF:wudfusb.IWDFUsbTargetPipe.IsInEndPoint
title: IWDFUsbTargetPipe::IsInEndPoint method
author: windows-driver-content
description: The IsInEndPoint method determines whether a USB pipe (endpoint) is an IN pipe.
old-location: wdf\iwdfusbtargetpipe_isinendpoint.htm
old-project: wdf
ms.assetid: c1cba1fa-3952-4f2f-829f-2f5983349df8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbTargetPipe, UMDFUSBref_07580c26-1173-4624-9199-c8dc8ef59edf.xml, wdf.iwdfusbtargetpipe_isinendpoint, IWDFUsbTargetPipe::IsInEndPoint, umdf.iwdfusbtargetpipe_isinendpoint, IsInEndPoint, wudfusb/IWDFUsbTargetPipe::IsInEndPoint, IWDFUsbTargetPipe interface, IsInEndPoint method, IsInEndPoint method, IsInEndPoint method, IWDFUsbTargetPipe interface
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
-	IWDFUsbTargetPipe.IsInEndPoint
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::IsInEndPoint method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsInEndPoint</b> method determines whether a USB pipe (endpoint) is an IN pipe.


## -syntax


````
BOOL  IsInEndPoint();
````


## -parameters





## -returns


<b>IsInEndPoint</b> returns a BOOL value that indicates whether the USB pipe is an IN pipe. <b>TRUE</b> indicates the pipe is an IN pipe. <b>FALSE</b> indicates the pipe is not an IN pipe.



## -remarks


If the USB pipe is an IN pipe, a UMDF driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a> method to format a read request. The framework can then send the request to the USB pipe.
<div class="alert"><b>Note</b>    The meaning of IN and OUT is opposite in WDF and USB.</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::IsInEndPoint method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

