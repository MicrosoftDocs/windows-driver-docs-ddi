---
UID: NS:ufxbase._UFX_DEVICE_CAPABILITIES
title: "_UFX_DEVICE_CAPABILITIES"
author: windows-driver-content
description: The UFX_DEVICE_CAPABILITIES structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.
old-location: buses\ufx_device_capabilities.htm
old-project: usbref
ms.assetid: 896919C9-E72E-4C0F-9E3E-9BEE9F55D27D
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: PUFX_DEVICE_CAPABILITIES structure pointer [Buses], UFX_DEVICE_CAPABILITIES, buses.ufx_device_capabilities, PUFX_DEVICE_CAPABILITIES, UFX_DEVICE_CAPABILITIES structure [Buses], *PUFX_DEVICE_CAPABILITIES, ufxbase/UFX_DEVICE_CAPABILITIES, _UFX_DEVICE_CAPABILITIES, ufxbase/PUFX_DEVICE_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ufxbase.h
apiname:
-	UFX_DEVICE_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PUFX_DEVICE_CAPABILITIES, UFX_DEVICE_CAPABILITIES"
req.product: Windows 10 or later.
---

# _UFX_DEVICE_CAPABILITIES structure


## -description


The <b>UFX_DEVICE_CAPABILITIES</b> structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.


## -syntax


````
typedef struct _UFX_DEVICE_CAPABILITIES {
  ULONG            Size;
  USB_DEVICE_SPEED MaxSpeed;
  ULONG            RemoteWakeSignalDelay;
  BOOLEAN          PdcpSupported;
  USHORT           InEndpointBitmap;
  USHORT           OutEndpointBitmap;
} UFX_DEVICE_CAPABILITIES, *PUFX_DEVICE_CAPABILITIES;
````


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

