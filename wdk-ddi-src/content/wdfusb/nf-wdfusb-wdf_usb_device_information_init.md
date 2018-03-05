---
UID: NF:wdfusb.WDF_USB_DEVICE_INFORMATION_INIT
title: WDF_USB_DEVICE_INFORMATION_INIT function
author: windows-driver-content
description: The WDF_USB_DEVICE_INFORMATION_INIT function initializes a driver's WDF_USB_DEVICE_INFORMATION structure.
old-location: wdf\wdf_usb_device_information_init.htm
old-project: wdf
ms.assetid: 8f4931d7-6b5f-412f-ace9-32f20dfa7c90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_ffde7966-f00b-4614-9845-aaebe2e0488b.xml, WDF_USB_DEVICE_INFORMATION_INIT, WDF_USB_DEVICE_INFORMATION_INIT function, kmdf.wdf_usb_device_information_init, wdf.wdf_usb_device_information_init, wdfusb/WDF_USB_DEVICE_INFORMATION_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_DEVICE_INFORMATION_INIT
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_USB_DEVICE_INFORMATION_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function initializes a driver's <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a> structure.


## -syntax


````
VOID WDF_USB_DEVICE_INFORMATION_INIT(
  _Out_ PWDF_USB_DEVICE_INFORMATION Udi
);
````


## -parameters




### -param Udi [out]

A pointer to the driver's <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_DEVICE_INFORMATION_INIT</b> function zeros the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a> structure and sets its <b>Size</b> member to the size of the structure.


#### Examples

For a code example that uses<b>WDF_USB_DEVICE_INFORMATION_INIT</b>, see <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceretrieveinformation.md">WdfUsbTargetDeviceRetrieveInformation</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_device_information.md">WDF_USB_DEVICE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_INFORMATION_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

