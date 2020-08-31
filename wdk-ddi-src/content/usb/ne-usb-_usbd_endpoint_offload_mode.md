---
UID: NE:usb._USBD_ENDPOINT_OFFLOAD_MODE
title: _USBD_ENDPOINT_OFFLOAD_MODE (usb.h)
description: Defines values for endpoint offloading options in the USB device or host controller.
old-location: buses\usbd_endpoint_offload_mode.htm
tech.root: usbref
ms.assetid: 577B2B5E-934E-4354-B6FF-FDFE9D1144D7
ms.date: 05/07/2018
keywords: ["USBD_ENDPOINT_OFFLOAD_MODE enumeration"]
ms.keywords: USBD_ENDPOINT_OFFLOAD_MODE, USBD_ENDPOINT_OFFLOAD_MODE enumeration [Buses], UsbdEndpointOffloadHardwareAssisted, UsbdEndpointOffloadModeNotSupported, UsbdEndpointOffloadSoftwareAssisted, _USBD_ENDPOINT_OFFLOAD_MODE, buses.usbd_endpoint_offload_mode, usb/USBD_ENDPOINT_OFFLOAD_MODE, usb/UsbdEndpointOffloadHardwareAssisted, usb/UsbdEndpointOffloadModeNotSupported, usb/UsbdEndpointOffloadSoftwareAssisted
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
targetos: Windows
req.typenames: USBD_ENDPOINT_OFFLOAD_MODE
f1_keywords:
 - _USBD_ENDPOINT_OFFLOAD_MODE
 - usb/_USBD_ENDPOINT_OFFLOAD_MODE
 - USBD_ENDPOINT_OFFLOAD_MODE
 - usb/USBD_ENDPOINT_OFFLOAD_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usb.h
api_name:
 - USBD_ENDPOINT_OFFLOAD_MODE
---

# _USBD_ENDPOINT_OFFLOAD_MODE enumeration


## -description

Defines values for endpoint offloading options in the USB device or host controller.

## -enum-fields

### -field UsbdEndpointOffloadModeNotSupported

Endpoint offloading is not supported.

### -field UsbdEndpointOffloadSoftwareAssisted

Endpoint offloading is handled by the software.

### -field UsbdEndpointOffloadHardwareAssisted

Endpoint offloading is handled in the USB device or host controller hardware.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406230(v=vs.85)">USBD_QueryUsbCapability</a>

