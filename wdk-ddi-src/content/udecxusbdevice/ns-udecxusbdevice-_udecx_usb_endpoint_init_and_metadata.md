---
UID: NS:udecxusbdevice._UDECX_USB_ENDPOINT_INIT_AND_METADATA
title: "_UDECX_USB_ENDPOINT_INIT_AND_METADATA"
author: windows-driver-content
description: Contains the descriptors supported by an endpoint of a virtual USB device.
old-location: buses\udecx_usb_endpoint_init_and_metadata.htm
old-project: usbref
ms.assetid: B68FD95B-E7B8-4748-A1D0-09A1F9763626
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, PUDECX_USB_ENDPOINT_INIT_AND_METADATA, PUDECX_USB_ENDPOINT_INIT_AND_METADATA structure pointer [Buses], UDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA structure [Buses], _UDECX_USB_ENDPOINT_INIT_AND_METADATA, buses.udecx_usb_endpoint_init_and_metadata, udecxusbdevice/PUDECX_USB_ENDPOINT_INIT_AND_METADATA, udecxusbdevice/UDECX_USB_ENDPOINT_INIT_AND_METADATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_USB_ENDPOINT_INIT_AND_METADATA
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# _UDECX_USB_ENDPOINT_INIT_AND_METADATA structure


## -description


Contains the descriptors supported by an endpoint of a virtual USB device.


## -struct-fields




### -field UdecxUsbEndpointInit

A pointer to a <b>UDECXUSBDEVICE_INIT</b> structure that contains initialization parameters for the virtual USB device. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>.


### -field EndpointDescriptorBufferLength

The length of the endpoint descriptor.


### -field EndpointDescriptor

Required. A buffer containing the endpoint descriptor. The descriptor is described in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structure.


### -field SuperSpeedEndpointCompanionDescriptor

Optional. A USB-defined SuperSpeed Endpoint Companion descriptor. For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification. The descriptor is described in a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406269">USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595914">EVT_UDECX_USB_DEVICE_ENDPOINT_ADD</a>
 

 

