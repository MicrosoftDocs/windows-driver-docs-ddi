---
UID: NS:udecxusbdevice._UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
title: _UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS (udecxusbdevice.h)
description: Initializes a UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure with pointers to callback functions that are implemented by a UDE client for a virtual USB device.
old-location: buses\udecx_usb_device_state_change_callbacks.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure"]
ms.keywords: "*PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure pointer [Buses], UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure [Buses], _UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, buses.udecx_usb_device_state_change_callbacks, udecxusbdevice/PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, udecxusbdevice/UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS"
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
targetos: Windows
req.typenames: UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS, *PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
f1_keywords:
 - _UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
 - udecxusbdevice/_UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
 - PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
 - udecxusbdevice/PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
 - UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
 - udecxusbdevice/UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UdecxUsbDevice.h
api_name:
 - UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS
---

# _UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure


## -description

Initializes a <b>UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</b> structure with pointers to callback functions that are implemented by a UDE client for a virtual USB device.

## -struct-fields

### -field Size

The size of this structure.

### -field EvtUsbDeviceLinkPowerEntry

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_entry">EVT_UDECX_USB_DEVICE_D0_ENTRY</a> callback function implemented by a UDE client driver.

### -field EvtUsbDeviceLinkPowerExit

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_exit">EVT_UDECX_USB_DEVICE_D0_EXIT</a> callback function implemented by a UDE client driver.

### -field EvtUsbDeviceSetFunctionSuspendAndWake

### -field EvtUsbDeviceReset

### -field EvtUsbDeviceDefaultEndpointAdd

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_default_endpoint_add">EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD</a> callback function implemented by a UDE client driver.

### -field EvtUsbDeviceEndpointAdd

A pointer to an E<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add">VT_UDECX_USB_DEVICE_ENDPOINT_ADD</a> callback function implemented by a UDE client driver.

### -field EvtUsbDeviceEndpointsConfigure

A pointer to an <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback function implemented by a UDE client driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a>
