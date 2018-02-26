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
ms.keywords: ",  , *, *PCONTROLLER_USB_20_HARDWARE_LPM_FLAGS, ,, 0, 2, A, B, C, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, CONTROLLER_USB_20_HARDWARE_LPM_FLAGS union [Buses], D, E, F, G, H, L, M, N, O, P, R, S, T, U, W, _, _CONTROLLER_USB_20_HARDWARE_LPM_FLAGS, buses._controller_usb_20_hardware_lpm_flags, ucxroothub/_CONTROLLER_USB_20_HARDWARE_LPM_FLAGS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxroothub.h
apiname:
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

 




#### - L1CapabilitySupported

Indicates support for L1 transitions.


#### - BeslLpmCapabilitySupported

Indicates Best Effort Service latency (BESL) latency support. 


## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_20port_info.md">ROOTHUB_20PORT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20CONTROLLER_USB_20_HARDWARE_LPM_FLAGS union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

