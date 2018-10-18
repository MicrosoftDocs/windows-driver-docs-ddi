---
UID: NF:wudfusb.IWDFUsbTargetPipe.GetInformation
title: IWDFUsbTargetPipe::GetInformation
author: windows-driver-content
description: The GetInformation method retrieves information about a USB pipe (endpoint).
old-location: wdf\iwdfusbtargetpipe_getinformation.htm
tech.root: wdf
ms.assetid: b1462a64-debf-441f-8964-4644074e5e53
ms.date: 2/26/2018
ms.keywords: GetInformation, GetInformation method, GetInformation method,IWDFUsbTargetPipe interface, IWDFUsbTargetPipe interface,GetInformation method, IWDFUsbTargetPipe.GetInformation, IWDFUsbTargetPipe::GetInformation, UMDFUSBref_4d7b2b77-fa26-45e2-8f3f-e0315d70f937.xml, umdf.iwdfusbtargetpipe_getinformation, wdf.iwdfusbtargetpipe_getinformation, wudfusb/IWDFUsbTargetPipe::GetInformation
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
-	IWDFUsbTargetPipe.GetInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe::GetInformation


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information about a USB pipe (endpoint).


## -parameters




### -param pInfo [out]

A pointer to a variable that receives USB pipe information.


## -returns



None




## -remarks



After a UMDF driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560339">IWDFUsbInterface::RetrieveUsbPipeObject</a> method to retrieve a USB pipe object, the UMDF driver should retrieve information about the USB pipe. Therefore, the <b>GetInformation</b> method does not fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560339">IWDFUsbInterface::RetrieveUsbPipeObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>
 

 

