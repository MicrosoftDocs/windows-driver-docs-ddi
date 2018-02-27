---
UID: NF:wudfusb.IWDFUsbTargetPipe.GetType
title: IWDFUsbTargetPipe::GetType method
author: windows-driver-content
description: The GetType method retrieves the type of a USB pipe.
old-location: wdf\iwdfusbtargetpipe_gettype.htm
old-project: wdf
ms.assetid: c8d76d5b-f388-4e22-ba57-d299ab3dee80
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetType method, GetType method, IWDFUsbTargetPipe interface, GetType,IWDFUsbTargetPipe.GetType, IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, GetType method, IWDFUsbTargetPipe::GetType, UMDFUSBref_792b0720-a0c3-45da-b5e8-7b2f3a0c3770.xml, umdf.iwdfusbtargetpipe_gettype, wdf.iwdfusbtargetpipe_gettype, wudfusb/IWDFUsbTargetPipe::GetType
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetPipe.GetType
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::GetType method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetType</b> method retrieves the type of a USB pipe.


## -syntax


````
USBD_PIPE_TYPE  GetType();
````


## -parameters






## -returns



<b>GetType</b> returns a USBD_PIPE_TYPE value that identifies the type of the USB pipe.




## -remarks



The <b>GetType</b> method is provided for convenience because a UMDF driver can obtain the type of the USB pipe from the <b>PipeType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540285">WINUSB_PIPE_INFORMATION</a> structure that the driver retrieves when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560403">IWDFUsbTargetPipe::GetInformation</a> method. 

For a code example of how to use the <b>GetType</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560403">IWDFUsbTargetPipe::GetInformation</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::GetType method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

