---
UID: NS:udecxusbdevice._UDECX_USB_ENDPOINT_INIT_AND_METADATA
title: _UDECX_USB_ENDPOINT_INIT_AND_METADATA (udecxusbdevice.h)
description: Contains the descriptors supported by an endpoint of a virtual USB device.
old-location: buses\udecx_usb_endpoint_init_and_metadata.htm
tech.root: usbref
ms.assetid: B68FD95B-E7B8-4748-A1D0-09A1F9763626
ms.date: 05/07/2018
keywords: ["_UDECX_USB_ENDPOINT_INIT_AND_METADATA structure"]
ms.keywords: "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, PUDECX_USB_ENDPOINT_INIT_AND_METADATA, PUDECX_USB_ENDPOINT_INIT_AND_METADATA structure pointer [Buses], UDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA structure [Buses], _UDECX_USB_ENDPOINT_INIT_AND_METADATA, buses.udecx_usb_endpoint_init_and_metadata, udecxusbdevice/PUDECX_USB_ENDPOINT_INIT_AND_METADATA, udecxusbdevice/UDECX_USB_ENDPOINT_INIT_AND_METADATA"
f1_keywords:
 - "udecxusbdevice/UDECX_USB_ENDPOINT_INIT_AND_METADATA"
 - "UDECX_USB_ENDPOINT_INIT_AND_METADATA"
req.header: udecxusbdevice.h
req.include-header: Udecx.h
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
- UdecxUsbDevice.h
api_name:
- UDECX_USB_ENDPOINT_INIT_AND_METADATA
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
---

# _UDECX_USB_ENDPOINT_INIT_AND_METADATA structure


## -description


Contains the descriptors supported by an endpoint of a virtual USB device.


## -struct-fields




### -field UdecxUsbEndpointInit

A pointer to a <b>UDECXUSBDEVICE_INIT</b> structure that contains initialization parameters for the virtual USB device. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>.


### -field EndpointDescriptorBufferLength

The length of the endpoint descriptor.


### -field EndpointDescriptor

Required. A buffer containing the endpoint descriptor. The descriptor is described in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structure.


### -field SuperSpeedEndpointCompanionDescriptor

Optional. A USB-defined SuperSpeed Endpoint Companion descriptor. For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification. The descriptor is described in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_superspeed_endpoint_companion_descriptor">USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add">EVT_UDECX_USB_DEVICE_ENDPOINT_ADD</a>
 

 

