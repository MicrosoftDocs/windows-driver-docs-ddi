---
UID: NE:usb._USBD_ENDPOINT_OFFLOAD_MODE
title: "_USBD_ENDPOINT_OFFLOAD_MODE"
author: windows-driver-content
description: Defines values for endpoint offloading options in the USB device or host controller.
old-location: buses\usbd_endpoint_offload_mode.htm
old-project: usbref
ms.assetid: 577B2B5E-934E-4354-B6FF-FDFE9D1144D7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, B, D, E, F, I, L, M, N, O, P, S, T, U, USBD_ENDPOINT_OFFLOAD_MODE, USBD_ENDPOINT_OFFLOAD_MODE enumeration [Buses], UsbdEndpointOffloadHardwareAssisted, UsbdEndpointOffloadModeNotSupported, UsbdEndpointOffloadSoftwareAssisted, _, _USBD_ENDPOINT_OFFLOAD_MODE, buses.usbd_endpoint_offload_mode, usb/USBD_ENDPOINT_OFFLOAD_MODE, usb/UsbdEndpointOffloadHardwareAssisted, usb/UsbdEndpointOffloadModeNotSupported, usb/UsbdEndpointOffloadSoftwareAssisted"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usb.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usb.h
apiname:
-	USBD_ENDPOINT_OFFLOAD_MODE
product: Windows
targetos: Windows
req.typenames: USBD_ENDPOINT_OFFLOAD_MODE
req.product: Windows 10 or later.
---

# _USBD_ENDPOINT_OFFLOAD_MODE enumeration


## -description


Defines values for endpoint offloading options in the USB device or host controller.


## -syntax


````
typedef enum _USBD_ENDPOINT_OFFLOAD_MODE { 
  UsbdEndpointOffloadModeNotSupported  = 0,
  UsbdEndpointOffloadSoftwareAssisted,
  UsbdEndpointOffloadHardwareAssisted
} USBD_ENDPOINT_OFFLOAD_MODE;
````


## -enum-fields




### -field UsbdEndpointOffloadModeNotSupported

Endpoint offloading is not supported.


### -field UsbdEndpointOffloadSoftwareAssisted

Endpoint offloading is handled by the software.


### -field UsbdEndpointOffloadHardwareAssisted

Endpoint offloading is handled in the USB device or host controller hardware.


## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_queryusbcapability.md">USBD_QueryUsbCapability</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ENDPOINT_OFFLOAD_MODE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

