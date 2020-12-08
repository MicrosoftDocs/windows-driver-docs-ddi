---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_ENDPOINT_ADD
title: EVT_UDECX_USB_DEVICE_ENDPOINT_ADD (udecxusbdevice.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create a dynamic endpoint on the virtual USB device.
old-location: buses\evt_udecx_usb_device_endpoint_add.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback function"]
ms.keywords: EVT_UDECX_USB_DEVICE_ENDPOINT_ADD, EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback, EvtUsbDeviceEndpointAdd, EvtUsbDeviceEndpointAdd callback function [Buses], buses.evt_udecx_usb_device_endpoint_add, udecxusbdevice/EvtUsbDeviceEndpointAdd
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UDECX_USB_DEVICE_ENDPOINT_ADD
 - udecxusbdevice/EVT_UDECX_USB_DEVICE_ENDPOINT_ADD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - UdecxUsbDevice.h
api_name:
 - EvtUsbDeviceEndpointAdd
---

# EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback function


## -description

The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create a dynamic endpoint on the virtual USB device.

## -parameters

### -param UdecxUsbDevice 

[in]
A handle to the UDE device object for which the client driver creates an endpoint. The driver created this object in a previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

### -param EndpointToCreate 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/udecxusbdevice/ns-udecxusbdevice-_udecx_usb_endpoint_init_and_metadata">UDECX_USB_ENDPOINT_INIT_AND_METADATA</a>             structure that contains the endpoint descriptor.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.

## -remarks

The client driver registered this callback function in a previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the implementation, the client driver is expected to create the endpoint by calling <a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a> by using the initialization parameters (<b>UDECXUSBENDPOINT_INIT</b>) passed by the class extension in the <a href="/windows-hardware/drivers/ddi/udecxusbdevice/ns-udecxusbdevice-_udecx_usb_endpoint_init_and_metadata">UDECX_USB_ENDPOINT_INIT_AND_METADATA</a> structure.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbendpoint/nf-udecxusbendpoint-udecxusbendpointcreate">UdecxUsbEndpointCreate</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
