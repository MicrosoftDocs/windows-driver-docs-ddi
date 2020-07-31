---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
title: _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION (usbioctl.h)
description: Contains registration information for the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request.
old-location: buses\usb_transport_characteristics_change_registration.htm
tech.root: usbref
ms.assetid: AC05B79E-D293-4EC7-8BF2-D14E3163FB43
ms.date: 05/07/2018
keywords: ["_USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure"]
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, buses.usb_transport_characteristics_change_registration, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION"
f1_keywords:
 - "usbioctl/USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION"
 - "USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION structure


## -description


Contains registration information for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request.


## -struct-fields




### -field ChangeNotificationInputFlags

 


### -field Handle

An opaque handle for this registration.


### -field UsbTransportCharacteristics

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_transport_characteristics">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics. 



#### - ULONG

A bitmask set by the client driver to register for change notifications that it is interested in. The following bits are valid:

If 

USB_REGISTER_FOR_TRANSPORT_LATENCY_CHANGE 

is set, the client is notified of changes in transport latency.  



If USB_REGISTER_FOR_TRANSPORT_BANDWIDTH_CHANGE 

is set, the client is notified of changes in bandwidth. 



## -remarks



The registration handle received in this request is valid until the caller sends the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_unregister_for_transport_characteristics_change">IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request to unregister for notifications.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_register_for_transport_characteristics_change">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>
 

 

