---
UID: NS:usbioctl._USB_HCD_DRIVERKEY_NAME
title: "_USB_HCD_DRIVERKEY_NAME"
author: windows-driver-content
description: The USB_HCD_DRIVERKEY_NAME structure is used with the IOCTL_GET_HCD_DRIVERKEY_NAME I/O control request to retrieve the driver key in the registry for the USB host controller driver.
old-location: buses\usb_hcd_driverkey_name.htm
old-project: usbref
ms.assetid: 01161a61-c52a-4a0e-b680-a8c3a224c2e5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUSB_HCD_DRIVERKEY_NAME, ,, A, B, C, D, E, H, I, K, M, N, P, PUSB_HCD_DRIVERKEY_NAME, PUSB_HCD_DRIVERKEY_NAME structure pointer [Buses], R, S, U, USB_HCD_DRIVERKEY_NAME, USB_HCD_DRIVERKEY_NAME structure [Buses], V, Y, _, _USB_HCD_DRIVERKEY_NAME, buses.usb_hcd_driverkey_name, usbioctl/PUSB_HCD_DRIVERKEY_NAME, usbioctl/USB_HCD_DRIVERKEY_NAME, usbstrct_f8c10863-dd1e-4771-b243-319a24f69f2a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_HCD_DRIVERKEY_NAME
product: Windows
targetos: Windows
req.typenames: USB_HCD_DRIVERKEY_NAME, *PUSB_HCD_DRIVERKEY_NAME
req.product: Windows 10 or later.
---

# _USB_HCD_DRIVERKEY_NAME structure


## -description


The <b>USB_HCD_DRIVERKEY_NAME</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_get_hcd_driverkey_name.md">IOCTL_GET_HCD_DRIVERKEY_NAME</a> I/O control request to retrieve the driver key in the registry for the USB host controller driver.


## -syntax


````
typedef struct _USB_HCD_DRIVERKEY_NAME {
  ULONG ActualLength;
  WCHAR DriverKeyName[1];
} USB_HCD_DRIVERKEY_NAME, *PUSB_HCD_DRIVERKEY_NAME;
````


## -struct-fields




### -field ActualLength

The length, in bytes, of the string in the <b>DriverKeyName</b> member.


### -field DriverKeyName

A NULL-terminated Unicode driver key name for the USB host controller.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_get_hcd_driverkey_name.md">IOCTL_GET_HCD_DRIVERKEY_NAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HCD_DRIVERKEY_NAME structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

