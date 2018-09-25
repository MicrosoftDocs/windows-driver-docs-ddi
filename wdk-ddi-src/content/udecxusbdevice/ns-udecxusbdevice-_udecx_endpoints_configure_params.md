---
UID: NS:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_PARAMS
title: "_UDECX_ENDPOINTS_CONFIGURE_PARAMS"
author: windows-driver-content
description: Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE.
old-location: buses\udecx_endpoints_configure_params.htm
tech.root: usbref
ms.assetid: C31AE3A8-CD3C-4270-BA5C-A61C0F386701
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: "*PUDECX_ENDPOINTS_CONFIGURE_PARAMS, PUDECX_ENDPOINTS_CONFIGURE_PARAMS, PUDECX_ENDPOINTS_CONFIGURE_PARAMS structure pointer [Buses], UDECX_ENDPOINTS_CONFIGURE_PARAMS, UDECX_ENDPOINTS_CONFIGURE_PARAMS structure [Buses], _UDECX_ENDPOINTS_CONFIGURE_PARAMS, buses.udecx_endpoints_configure_params, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_PARAMS, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_PARAMS"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_ENDPOINTS_CONFIGURE_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UDECX_ENDPOINTS_CONFIGURE_PARAMS, *PUDECX_ENDPOINTS_CONFIGURE_PARAMS
---

# _UDECX_ENDPOINTS_CONFIGURE_PARAMS structure


## -description


Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes <a href="https://msdn.microsoft.com/library/windows/hardware/mt595913">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>.


## -struct-fields




### -field Size

Size of this structure.


### -field ConfigureType

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt627994">UDECX_ENDPOINTS_CONFIGURE_TYPE</a>-typed value that indicates whether the configuration, interface setting, or endpoint must be configured. 


### -field NewConfigurationValue

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeDeviceConfigurationChange</b>, this value is <b>bConfigurationValue</b> of the new configuration descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>).


### -field InterfaceNumber

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bInterfaceNumber</b> of the current interface descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>).


### -field NewInterfaceSetting

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bAlternateSetting</b> of the interface descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>) to set.


### -field EndpointsToConfigureCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints that must be configured.


### -field EndpointsToConfigure

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects to be configured.

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects that must be released.


### -field ReleasedEndpointsCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints to release.


### -field ReleasedEndpoints

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595913">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>
 

 

