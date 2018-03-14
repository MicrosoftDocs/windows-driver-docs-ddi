---
UID: NS:ucxroothub._CONTROLLER_USB_20_HARDWARE_LPM_FLAGS
title: "_CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
author: windows-driver-content
description: Describes supported protocol capabilities for Link Power Management (LPM) in as defined the USB 2.0 specification.
old-location: buses\_controller_usb_20_hardware_lpm_flags.htm
old-project: usbref
ms.assetid: B8CEBCEA-7F1F-4E4B-B04E-D914D5875027
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PCONTROLLER_USB_20_HARDWARE_LPM_FLAGS, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS union [Buses], _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, buses._controller_usb_20_hardware_lpm_flags, ucxroothub/_CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	CONTROLLER_USB_20_HARDWARE_LPM_FLAGS
product: Windows
targetos: Windows
req.typenames: CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, *PCONTROLLER_USB_20_HARDWARE_LPM_FLAGS
req.product: Windows 10 or later.
---

# _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS structure


## -description


Describes supported protocol capabilities for Link Power Management (LPM) in as defined the USB 2.0 specification.


## -syntax


````
typedef union _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS {
  UCHAR  AsUchar;
  struct {
    ULONG L1CapabilitySupported  :1;
    ULONG BeslLpmCapabilitySupported  :1;
  };
} CONTROLLER_USB_20_HARDWARE_LPM_FLAGS;
````


## -struct-fields




### -field AsUchar

The size of structure represented as a char (8-bit) value.


### -field Flags

 




#### - BeslLpmCapabilitySupported

Indicates Best Effort Service latency (BESL) latency support. 


#### - L1CapabilitySupported

Indicates support for L1 transitions.


## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_20port_info.md">ROOTHUB_20PORT_INFO</a>



 

 


