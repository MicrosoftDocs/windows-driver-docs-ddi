---
UID: NS:ufxbase._UFX_DEVICE_CAPABILITIES
title: _UFX_DEVICE_CAPABILITIES (ufxbase.h)
description: The UFX_DEVICE_CAPABILITIES structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.
old-location: buses\ufx_device_capabilities.htm
tech.root: usbref
ms.assetid: 896919C9-E72E-4C0F-9E3E-9BEE9F55D27D
ms.date: 05/07/2018
keywords: ["_UFX_DEVICE_CAPABILITIES structure"]
ms.keywords: "*PUFX_DEVICE_CAPABILITIES, PUFX_DEVICE_CAPABILITIES, PUFX_DEVICE_CAPABILITIES structure pointer [Buses], UFX_DEVICE_CAPABILITIES, UFX_DEVICE_CAPABILITIES structure [Buses], _UFX_DEVICE_CAPABILITIES, buses.ufx_device_capabilities, ufxbase/PUFX_DEVICE_CAPABILITIES, ufxbase/UFX_DEVICE_CAPABILITIES"
f1_keywords:
 - "ufxbase/UFX_DEVICE_CAPABILITIES"
 - "UFX_DEVICE_CAPABILITIES"
req.header: ufxbase.h
req.include-header: 
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
- ufxbase.h
api_name:
- UFX_DEVICE_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: UFX_DEVICE_CAPABILITIES, *PUFX_DEVICE_CAPABILITIES
---

# _UFX_DEVICE_CAPABILITIES structure


## -description


The <b>UFX_DEVICE_CAPABILITIES</b> structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.


## -struct-fields




### -field Size

Size of the <b>UFX_DEVICE_CAPABILITIES</b> structure.


### -field MaxSpeed

Indicates the maximum USB speed supported by the device.


### -field RemoteWakeSignalDelay

The minimum time interval in milliseconds to wait after being suspended before requesting remote wakeup.


### -field PdcpSupported

If  <b>true</b>, indicates the client driver supports proprietary charger detection.


### -field InEndpointBitmap

A bitmap that defines which endpoint numbers can support an IN endpoint.  Bit 0 indicates endpoint address 0, bit 1 indicates endpoint address 1, etc.   Bit 0 (the default control endpoint) is required to be set to 1.


### -field OutEndpointBitmap

A bitmap that defines which endpoint numbers can support an OUT endpoint.  Bit 0 indicates endpoint address 0, bit 1 indicates endpoint address 1, etc.   Bit 0 (the default control endpoint) is required to be set to 1.

### -field SharesConnectors
A boolean value that indicates the connector supports multiple connectors.
 
### -field GroupId
 The group identifier the shared connector group to which a  controller will be added.
