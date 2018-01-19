---
UID: NS:windot11._DOT11_WPS_DEVICE_NAME
title: _DOT11_WPS_DEVICE_NAME
author: windows-driver-content
description: The DOT11_WPS_DEVICE_NAME structure contains a friendly name of the P2P device.
old-location: netvista\dot11_wps_device_name.htm
old-project: netvista
ms.assetid: 6C2B8E87-A88F-4244-81B2-0241E2DAE756
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WPS_DEVICE_NAME
req.alt-loc: Windot11.h
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
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# _DOT11_WPS_DEVICE_NAME structure



## -description

## -syntax

````
typedef struct _DOT11_WPS_DEVICE_NAME {
   ULONG  
uDeviceNameLength;
  UCHAR   ucDeviceName[DOT11_WPS_DEVICE_NAME_MAX_LENGTH];
} DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME;
````


## -struct-fields

### -field 
uDeviceNameLength</b>
<dd>
The length, in bytes, of the device name.


### -field ucDeviceName[DOT11_WPS_DEVICE_NAME_MAX_LENGTH]

A UTF-8–encoded descriptive name of the device.


## -remarks
