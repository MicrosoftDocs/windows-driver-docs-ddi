---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS
title: "_USB_TRANSPORT_CHARACTERISTICS"
author: windows-driver-content
description: Stores the transport characteristics at relevant points in time. This structure is used in the IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS request.
old-location: buses\usb_transport_characteristics.htm
old-project: usbref
ms.assetid: 56394A88-7231-4693-8DD1-C5C7586E490C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS, PUSB_TRANSPORT_CHARACTERISTICS, PUSB_TRANSPORT_CHARACTERISTICS structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS, USB_TRANSPORT_CHARACTERISTICS structure [Buses], _USB_TRANSPORT_CHARACTERISTICS, buses.usb_transport_characteristics, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS, usbioctl/USB_TRANSPORT_CHARACTERISTICS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	USB_TRANSPORT_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS, *PUSB_TRANSPORT_CHARACTERISTICS
req.product: Windows 10 or later.
---

# _USB_TRANSPORT_CHARACTERISTICS structure


## -description


Stores the transport characteristics at relevant points in time. This structure is used in the  <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_transport_characteristics.md">IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS</a> request.


## -syntax


````
typedef struct _USB_TRANSPORT_CHARACTERISTICS {
  ULONG                       Version;
  ULONG                       TransportCharacteristicsFlags;
  ULONG64                     CurrentRoundtripLatencyInMilliSeconds;
  ULONG64                     MaxPotentialBandwidth;
} USB_TRANSPORT_CHARACTERISTICS, *PUSB_TRANSPORT_CHARACTERISTICS;
````


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

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_transport_characteristics.md">IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_TRANSPORT_CHARACTERISTICS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

