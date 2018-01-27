---
UID: NF:wudfusb.IWDFUsbInterface.GetInterfaceNumber
title: IWDFUsbInterface::GetInterfaceNumber method
author: windows-driver-content
description: The GetInterfaceNumber method retrieves the index of a USB interface.
old-location: wdf\iwdfusbinterface_getinterfacenumber.htm
old-project: wdf
ms.assetid: de8de14a-94a8-49e2-912a-9c174f5a2c74
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfusb/IWDFUsbInterface::GetInterfaceNumber, GetInterfaceNumber method, IWDFUsbInterface interface, IWDFUsbInterface::GetInterfaceNumber, IWDFUsbInterface, wdf.iwdfusbinterface_getinterfacenumber, IWDFUsbInterface interface, GetInterfaceNumber method, GetInterfaceNumber, UMDFUSBref_4f4d9bc1-a1a1-4cc4-87ba-522fa3f8a0f7.xml, GetInterfaceNumber method, umdf.iwdfusbinterface_getinterfacenumber
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
-	IWDFUsbInterface.GetInterfaceNumber
product: Windows
targetos: Windows
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbInterface::GetInterfaceNumber method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInterfaceNumber</b> method retrieves the index of a USB interface.


## -syntax


````
UCHAR GetInterfaceNumber();
````


## -parameters





## -returns


<b>GetInterfaceNumber</b> returns the index of the USB interface.



## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetInterfaceNumber method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

