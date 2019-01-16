---
UID: NF:wudfusb.IWDFUsbTargetPipe.GetType
title: IWDFUsbTargetPipe::GetType
description: The GetType method retrieves the type of a USB pipe.
old-location: wdf\iwdfusbtargetpipe_gettype.htm
tech.root: wdf
ms.assetid: c8d76d5b-f388-4e22-ba57-d299ab3dee80
ms.date: 02/26/2018
ms.keywords: GetType, GetType method, GetType method,IWDFUsbTargetPipe interface, IWDFUsbTargetPipe interface,GetType method, IWDFUsbTargetPipe.GetType, IWDFUsbTargetPipe::GetType, UMDFUSBref_792b0720-a0c3-45da-b5e8-7b2f3a0c3770.xml, umdf.iwdfusbtargetpipe_gettype, wdf.iwdfusbtargetpipe_gettype, wudfusb/IWDFUsbTargetPipe::GetType
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
-	IWDFUsbTargetPipe.GetType
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe::GetType


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetType</b> method retrieves the type of a USB pipe.


## -parameters






## -returns



<b>GetType</b> returns a USBD_PIPE_TYPE value that identifies the type of the USB pipe.




## -remarks



The <b>GetType</b> method is provided for convenience because a UMDF driver can obtain the type of the USB pipe from the <b>PipeType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540285">WINUSB_PIPE_INFORMATION</a> structure that the driver retrieves when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560403">IWDFUsbTargetPipe::GetInformation</a> method. 

For a code example of how to use the <b>GetType</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560403">IWDFUsbTargetPipe::GetInformation</a>
 

 

