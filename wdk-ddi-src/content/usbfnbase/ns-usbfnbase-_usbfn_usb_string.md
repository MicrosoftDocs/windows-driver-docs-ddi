---
UID: NS:usbfnbase._USBFN_USB_STRING
title: "_USBFN_USB_STRING"
author: windows-driver-content
description: Describes a USB string descriptor and the associated string index.
old-location: buses\usbfn_usb_string.htm
old-project: usbref
ms.assetid: 1169A369-0E6D-4308-ABF6-0724FED73AF9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUSBFN_USB_STRING, ,, B, F, G, I, N, P, PUSBFN_USB_STRING, PUSBFN_USB_STRING structure pointer [Buses], R, S, T, U, USBFN_USB_STRING, USBFN_USB_STRING structure [Buses], _, _USBFN_USB_STRING, buses.usbfn_usb_string, usbfnbase/PUSBFN_USB_STRING, usbfnbase/USBFN_USB_STRING"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnbase.h
apiname:
-	USBFN_USB_STRING
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# _USBFN_USB_STRING structure


## -description


Describes a USB string descriptor and the associated string index. 


## -syntax


````
typedef struct _USBFN_USB_STRING {
  UINT8 StringIndex;
  WCHAR  UsbString[MAX_USB_STRING_LENGTH];
} USBFN_USB_STRING, *PUSBFN_USB_STRING;
````


## -struct-fields




### -field StringIndex

The string index.


### -field UsbString

Pointer to the string.  


## -see-also

<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_register_usb_string.md">IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_USB_STRING structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

