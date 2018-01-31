---
UID: NF:wudfusb.IWDFUsbInterface.GetConfiguredSettingIndex
title: IWDFUsbInterface::GetConfiguredSettingIndex method
author: windows-driver-content
description: The GetConfiguredSettingIndex method retrieves the current setting index for a USB interface.
old-location: wdf\iwdfusbinterface_getconfiguredsettingindex.htm
old-project: wdf
ms.assetid: 0deccfee-34e3-47ee-b141-9758cffcd0c2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbInterface, GetConfiguredSettingIndex, GetConfiguredSettingIndex method, IWDFUsbInterface interface, GetConfiguredSettingIndex method, wudfusb/IWDFUsbInterface::GetConfiguredSettingIndex, IWDFUsbInterface::GetConfiguredSettingIndex, wdf.iwdfusbinterface_getconfiguredsettingindex, UMDFUSBref_5c2cdbd4-d660-4933-b1fb-a99852b5cba8.xml, umdf.iwdfusbinterface_getconfiguredsettingindex, IWDFUsbInterface interface, GetConfiguredSettingIndex method
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
-	IWDFUsbInterface.GetConfiguredSettingIndex
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbInterface::GetConfiguredSettingIndex method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetConfiguredSettingIndex</b> method retrieves the current setting index for a USB interface.


## -syntax


````
UCHAR GetConfiguredSettingIndex();
````


## -parameters





## -returns


<b>GetConfiguredSettingIndex</b> returns the current setting index for the USB interface.



## -remarks


The <b>GetConfiguredSettingIndex</b> method is provided for convenience because a UMDF driver can obtain the current setting index from the <b>bAlternateSetting</b> member of the <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that the driver retrieves when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a> method. 



## -see-also

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560320">IWDFUsbInterface::GetInterfaceDescriptor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::GetConfiguredSettingIndex method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

