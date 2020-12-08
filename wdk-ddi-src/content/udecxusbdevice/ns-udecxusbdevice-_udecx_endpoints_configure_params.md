---
UID: NS:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_PARAMS
title: _UDECX_ENDPOINTS_CONFIGURE_PARAMS (udecxusbdevice.h)
description: Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE.
old-location: buses\udecx_endpoints_configure_params.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UDECX_ENDPOINTS_CONFIGURE_PARAMS structure"]
ms.keywords: "*PUDECX_ENDPOINTS_CONFIGURE_PARAMS, PUDECX_ENDPOINTS_CONFIGURE_PARAMS, PUDECX_ENDPOINTS_CONFIGURE_PARAMS structure pointer [Buses], UDECX_ENDPOINTS_CONFIGURE_PARAMS, UDECX_ENDPOINTS_CONFIGURE_PARAMS structure [Buses], _UDECX_ENDPOINTS_CONFIGURE_PARAMS, buses.udecx_endpoints_configure_params, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_PARAMS, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_PARAMS"
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
req.typenames: UDECX_ENDPOINTS_CONFIGURE_PARAMS, *PUDECX_ENDPOINTS_CONFIGURE_PARAMS
f1_keywords:
 - _UDECX_ENDPOINTS_CONFIGURE_PARAMS
 - udecxusbdevice/_UDECX_ENDPOINTS_CONFIGURE_PARAMS
 - PUDECX_ENDPOINTS_CONFIGURE_PARAMS
 - udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_PARAMS
 - UDECX_ENDPOINTS_CONFIGURE_PARAMS
 - udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UdecxUsbDevice.h
api_name:
 - UDECX_ENDPOINTS_CONFIGURE_PARAMS
---

# _UDECX_ENDPOINTS_CONFIGURE_PARAMS structure


## -description

Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>.

## -struct-fields

### -field Size

Size of this structure.

### -field ConfigureType

A <a href="/windows-hardware/drivers/ddi/udecxusbdevice/ne-udecxusbdevice-_udecx_endpoints_configure_type">UDECX_ENDPOINTS_CONFIGURE_TYPE</a>-typed value that indicates whether the configuration, interface setting, or endpoint must be configured.

### -field NewConfigurationValue

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeDeviceConfigurationChange</b>, this value is <b>bConfigurationValue</b> of the new configuration descriptor (<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>).

### -field InterfaceNumber

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bInterfaceNumber</b> of the current interface descriptor (<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>).

### -field NewInterfaceSetting

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bAlternateSetting</b> of the interface descriptor (<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>) to set.

### -field EndpointsToConfigureCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints that must be configured.

### -field EndpointsToConfigure

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects to be configured.

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects that must be released.

### -field ReleasedEndpointsCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints to release.

### -field ReleasedEndpoints

## -see-also

<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>
