---
UID: NA:usbfnbase
ms.assetid: f54db437-6d89-377b-8e79-ed49a7490c17
ms.author: windowsdriverdev
ms.date: 04/20/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbfnbase.h header





This header is used by usbref. For more information, see:

- [Universal Serial Bus (USB)](../_usbref/index.md)

This section contains reference topics for the Usbfnbase.h header.


In this section


Topic
Description




ALTERNATE_INTERFACE



The ALTERNATE_INTERFACE structure provides information about alternate settings for a Universal Serial Bus (USB) interface.





USBFN_BUS_CONFIGURATION_INFO



Configuration packet that stores information about 
an available USB configuration.





USBFN_BUS_SPEED







USBFN_CLASS_INFORMATION_PACKET_EX



Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions. 





USBFN_CLASS_INFORMATION_PACKET



Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.





USBFN_CLASS_INTERFACE



Describes an interface and its endpoints.





USBFN_DEVICE_STATE



Defines the USB device states for the device/controller.  These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.





USBFN_DIRECTION



Defines the USB data transfer direction types.





USBFN_EVENT



Defines notifications sent to class drivers.





USBFN_INTERFACE_INFO



Describes an interface and its endpoints.





USBFN_NOTIFICATION



Describes information about a USB  event notification that was 
		received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
		





USBFN_PIPE_INFORMATION



Describes attributes of a pipe associated with an endpoint on a specific interface.





USBFN_PORT_TYPE



Defines the possible port types that can be returned by the client driver during port detection.





USBFN_USB_STRING



Describes a USB string descriptor and the associated string index. 



 


Send comments about this topic to Microsoft

