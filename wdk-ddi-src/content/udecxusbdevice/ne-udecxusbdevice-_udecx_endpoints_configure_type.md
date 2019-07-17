---
UID: NE:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_TYPE
title: _UDECX_ENDPOINTS_CONFIGURE_TYPE (udecxusbdevice.h)
description: Defines values for endpoint configuration options.
old-location: buses\udecx_endpoints_configure_type.htm
tech.root: usbref
ms.assetid: F13C7D8D-C134-432A-904B-7435894B07E5
ms.date: 05/07/2018
ms.keywords: "*PUDECX_ENDPOINTS_CONFIGURE_TYPE, PUDECX_ENDPOINTS_CONFIGURE_TYPE, PUDECX_ENDPOINTS_CONFIGURE_TYPE enumeration pointer [Buses], UDECX_ENDPOINTS_CONFIGURE_TYPE, UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration [Buses], UdecxEndpointsConfigureTypeDeviceConfigurationChange, UdecxEndpointsConfigureTypeDeviceInitialize, UdecxEndpointsConfigureTypeEndpointsReleasedOnly, UdecxEndpointsConfigureTypeInterfaceSettingChange, _UDECX_ENDPOINTS_CONFIGURE_TYPE, buses.udecx_endpoints_configure_type, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceConfigurationChange, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceInitialize, udecxusbdevice/UdecxEndpointsConfigureTypeEndpointsReleasedOnly, udecxusbdevice/UdecxEndpointsConfigureTypeInterfaceSettingChange"
ms.topic: enum
f1_keywords:
 - "udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_TYPE"
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
- udecxusbdevice.h
api_name:
- UDECX_ENDPOINTS_CONFIGURE_TYPE
product:
- Windows
targetos: Windows
req.typenames: UDECX_ENDPOINTS_CONFIGURE_TYPE, *PUDECX_ENDPOINTS_CONFIGURE_TYPE
---

# _UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration


## -description


Defines values for endpoint configuration options. 


## -enum-fields




### -field UdecxEndpointsConfigureTypeDeviceInitialize

Reserved for internal use.


### -field UdecxEndpointsConfigureTypeDeviceConfigurationChange

The requested change applies to the USB device configuration.


### -field UdecxEndpointsConfigureTypeInterfaceSettingChange

The requested change applies to an alternate setting of a USB interface.


### -field UdecxEndpointsConfigureTypeEndpointsReleasedOnly

The requested change applies to an endpoint of an interface setting.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/ns-udecxusbdevice-_udecx_endpoints_configure_params">UDECX_ENDPOINTS_CONFIGURE_PARAMS</a>
 

 

