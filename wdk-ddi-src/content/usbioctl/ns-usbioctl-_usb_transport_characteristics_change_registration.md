---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
title: "_USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION"
author: windows-driver-content
description: Contains registration information for the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request.
old-location: buses\usb_transport_characteristics_change_registration.htm
old-project: usbref
ms.assetid: AC05B79E-D293-4EC7-8BF2-D14E3163FB43
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure [Buses], PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure pointer [Buses], buses.usb_transport_characteristics_change_registration, USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
req.product: Windows 10 or later.
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure


## -description


Contains registration information for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request.


## -syntax


````
typedef struct _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION {
  ChangeNotificationInputFlags    ULONG;
  USB_CHANGE_REGISTRATION_HANDLE  Handle;
   USB_TRANSPORT_CHARACTERISTICS  UsbTransportCharacteristics;
} USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION;
````


## -struct-fields




### -field ChangeNotificationInputFlags

 


### -field Handle

An opaque handle for this registration.


### -field UsbTransportCharacteristics

A <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics.md">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics. 



#### - ULONG

A bitmask set by the client driver to register for change notifications that it is interested in. The following bits are valid:

If 

USB_REGISTER_FOR_TRANSPORT_LATENCY_CHANGE 

is set, the client is notified of changes in transport latency.  



If USB_REGISTER_FOR_TRANSPORT_BANDWIDTH_CHANGE 

is set, the client is notified of changes in bandwidth. 



## -remarks



The registration handle received in this request is valid until the caller sends the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change.md">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request to unregister for notifications.




## -see-also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change.md">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

