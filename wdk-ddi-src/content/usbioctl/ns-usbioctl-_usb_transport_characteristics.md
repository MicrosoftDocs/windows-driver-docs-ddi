---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS
title: _USB_TRANSPORT_CHARACTERISTICS (usbioctl.h)
description: Stores the transport characteristics at relevant points in time. This structure is used in the IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS request.
old-location: buses\usb_transport_characteristics.htm
tech.root: usbref
ms.assetid: 56394A88-7231-4693-8DD1-C5C7586E490C
ms.date: 05/07/2018
keywords: ["USB_TRANSPORT_CHARACTERISTICS structure"]
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS, PUSB_TRANSPORT_CHARACTERISTICS, PUSB_TRANSPORT_CHARACTERISTICS structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS, USB_TRANSPORT_CHARACTERISTICS structure [Buses], _USB_TRANSPORT_CHARACTERISTICS, buses.usb_transport_characteristics, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS, usbioctl/USB_TRANSPORT_CHARACTERISTICS"
f1_keywords:
 - "usbioctl/USB_TRANSPORT_CHARACTERISTICS"
 - "USB_TRANSPORT_CHARACTERISTICS"
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- USB_TRANSPORT_CHARACTERISTICS
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS, *PUSB_TRANSPORT_CHARACTERISTICS
---

# _USB_TRANSPORT_CHARACTERISTICS structure


## -description


Stores the transport characteristics at relevant points in time. This structure is used in the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_transport_characteristics">IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS</a> request.


## -struct-fields




### -field Version

The version is set to  USB_TRANSPORT_CHARACTERISTICS_VERSION_1. 



### -field TransportCharacteristicsFlags

A bitmask that indicates to the client driver the transport characteristics that are available and are returned in this structure. 




If USB_TRANSPORT_CHARACTERISTICS_LATENCY_AVAILABLE 

is set, <b>CurrentRoundtripLatencyInMilliSeconds</b> contains valid information. Otherwise , it must not be used by the client driver. 




If USB_TRANSPORT_CHARACTERISTICS_BANDWIDTH_AVAILABLE 

is set, <b>MaxPotentialBandwidth</b> contains valid information. Otherwise, it must not be used by the client driver.  


### -field CurrentRoundtripLatencyInMilliSeconds

Contains the current round-trip delay in milliseconds from the time a non-isochronous transfer is received by the USB driver stack to the time that the transfer is completed.  

For MA-USB, the underlying network could be WiFi, WiGig, Ethernet etc. The delay can vary depending on the underlying network conditions. A client driver should query the latency periodically or whenever it is notified of a change. 



### -field MaxPotentialBandwidth

Contains the total bandwidth of the host controller’s shared transport. 

For MA-USB, the underlying network transport could be WiFi, WiGig, Ethernet etc. The total available bandwidth can vary depending on several factors such as the negotiation WiFi channel. A client driver should query the total bandwidth periodically or whenever it is notified of a change. 



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_transport_characteristics">IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS</a>
 

 

