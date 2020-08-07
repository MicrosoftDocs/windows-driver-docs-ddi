---
UID: NS:ucxroothub._CONTROLLER_USB_20_HARDWARE_LPM_FLAGS
title: _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS (ucxroothub.h)
description: Describes supported protocol capabilities for Link Power Management (LPM) in as defined the USB 2.0 specification.
old-location: buses\_controller_usb_20_hardware_lpm_flags.htm
tech.root: usbref
ms.assetid: B8CEBCEA-7F1F-4E4B-B04E-D914D5875027
ms.date: 05/07/2018
keywords: ["CONTROLLER_USB_20_HARDWARE_LPM_FLAGS structure"]
ms.keywords: "*PCONTROLLER_USB_20_HARDWARE_LPM_FLAGS, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS union [Buses], _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, buses._controller_usb_20_hardware_lpm_flags, ucxroothub/_CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
f1_keywords:
 - "ucxroothub/CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
 - "CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxroothub.h
api_name:
- CONTROLLER_USB_20_HARDWARE_LPM_FLAGS
targetos: Windows
req.typenames: CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, *PCONTROLLER_USB_20_HARDWARE_LPM_FLAGS
---

# _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS structure


## -description


Describes supported protocol capabilities for Link Power Management (LPM) in as defined the USB 2.0 specification.


## -struct-fields




### -field AsUchar

The size of structure represented as a char (8-bit) value.


### -field Flags

 


### -field Flags.L1CapabilitySupported

 


### -field Flags.BeslLpmCapabilitySupported

 


### -field L1CapabilitySupported

Indicates support for L1 transitions.


### -field BeslLpmCapabilitySupported

Indicates Best Effort Service latency (BESL) latency support. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxroothub/ns-ucxroothub-_roothub_20port_info">ROOTHUB_20PORT_INFO</a>
 

 

