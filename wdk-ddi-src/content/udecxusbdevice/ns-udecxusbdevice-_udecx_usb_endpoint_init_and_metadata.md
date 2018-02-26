---
UID: NS:udecxusbdevice._UDECX_USB_ENDPOINT_INIT_AND_METADATA
title: "_UDECX_USB_ENDPOINT_INIT_AND_METADATA"
author: windows-driver-content
description: Contains the descriptors supported by an endpoint of a virtual USB device.
old-location: buses\udecx_usb_endpoint_init_and_metadata.htm
old-project: usbref
ms.assetid: B68FD95B-E7B8-4748-A1D0-09A1F9763626
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA, ,, A, B, C, D, E, I, M, N, O, P, PUDECX_USB_ENDPOINT_INIT_AND_METADATA, PUDECX_USB_ENDPOINT_INIT_AND_METADATA structure pointer [Buses], S, T, U, UDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA structure [Buses], X, _, _UDECX_USB_ENDPOINT_INIT_AND_METADATA, buses.udecx_usb_endpoint_init_and_metadata, udecxusbdevice/PUDECX_USB_ENDPOINT_INIT_AND_METADATA, udecxusbdevice/UDECX_USB_ENDPOINT_INIT_AND_METADATA"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	UdecxUsbDevice.h
apiname:
-	UDECX_USB_ENDPOINT_INIT_AND_METADATA
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---

# _UDECX_USB_ENDPOINT_INIT_AND_METADATA structure


## -description


Contains the descriptors supported by an endpoint of a virtual USB device.


## -syntax


````
typedef struct _UDECX_USB_ENDPOINT_INIT_AND_METADATA {
  PUDECXUSBENDPOINT_INIT                                                                UdecxUsbEndpointInit;
   _Field_range_(sizeof(USB_ENDPOINT_DESCRIPTOR), 0xff) ULONG                           EndpointDescriptorBufferLength;
  _Notnull_ _Field_size_bytes_(EndpointDescriptorBufferLength) PUSB_ENDPOINT_DESCRIPTOR EndpointDescriptor;
  _Maybenull_ PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR                             SuperSpeedEndpointCompanionDescriptor;
} UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA;
````


## -struct-fields




### -field UdecxUsbEndpointInit

A pointer to a <b>UDECXUSBDEVICE_INIT</b> structure that contains initialization parameters for the virtual USB device. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>.


### -field EndpointDescriptorBufferLength

The length of the endpoint descriptor.


### -field EndpointDescriptor

Required. A buffer containing the endpoint descriptor. The descriptor is described in a <a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a> structure.


### -field SuperSpeedEndpointCompanionDescriptor

Optional. A USB-defined SuperSpeed Endpoint Companion descriptor. For more information, see section 9.6.7 and Table 9-20 in the official USB 3.0 specification. The descriptor is described in a <a href="..\usbspec\ns-usbspec-_usb_superspeed_endpoint_companion_descriptor.md">USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR</a> structure.


## -see-also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add.md">EVT_UDECX_USB_DEVICE_ENDPOINT_ADD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_ENDPOINT_INIT_AND_METADATA structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

