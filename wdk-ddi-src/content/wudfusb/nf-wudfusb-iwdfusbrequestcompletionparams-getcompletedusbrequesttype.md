---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetCompletedUsbRequestType
title: IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method
author: windows-driver-content
description: The GetCompletedUsbRequestType method retrieves the type of operation that the request to be completed contains.
old-location: wdf\iwdfusbrequestcompletionparams_getcompletedusbrequesttype.htm
old-project: wdf
ms.assetid: ce20ed09-2f4d-4cc0-9185-a3a72dd73165
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbRequestCompletionParams, IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType, IWDFUsbRequestCompletionParams interface, GetCompletedUsbRequestType method, wudfusb/IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType, UMDFRequestObjectRef_9b863f1d-1684-4d87-a7a0-41747dba6aff.xml, GetCompletedUsbRequestType method, IWDFUsbRequestCompletionParams interface, GetCompletedUsbRequestType method, wdf.iwdfusbrequestcompletionparams_getcompletedusbrequesttype, umdf.iwdfusbrequestcompletionparams_getcompletedusbrequesttype, GetCompletedUsbRequestType
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
-	IWDFUsbRequestCompletionParams.GetCompletedUsbRequestType
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletedUsbRequestType</b> method retrieves the type of operation that the request to be completed contains.


## -syntax


````
WDF_USB_REQUEST_TYPE  GetCompletedUsbRequestType();
````


## -parameters





## -returns


<b>GetCompletedUsbRequestType</b> returns a value of type <a href="..\wudfusb\ne-wudfusb-_wdf_usb_request_type.md">WDF_USB_REQUEST_TYPE</a> that identifies the USB request type.



## -see-also

<a href="..\wudfusb\ne-wudfusb-_wdf_usb_request_type.md">WDF_USB_REQUEST_TYPE</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbrequestcompletionparams.md">IWDFUsbRequestCompletionParams</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

