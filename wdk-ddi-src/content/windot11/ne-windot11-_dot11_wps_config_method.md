---
UID: NE:windot11._DOT11_WPS_CONFIG_METHOD
title: _DOT11_WPS_CONFIG_METHOD
author: windows-driver-content
description: The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.
old-location: netvista\dot11_wps_config_method.htm
old-project: netvista
ms.assetid: FFA5B3FF-57AF-4701-97FB-E1182CDE8F7A
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD, *PDOT11_WPS_CONFIG_METHOD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WPS_CONFIG_METHOD
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
req.typenames: DOT11_WPS_CONFIG_METHOD, *PDOT11_WPS_CONFIG_METHOD
req.product: Windows 10 or later.
---

# _DOT11_WPS_CONFIG_METHOD enumeration



## -description

## -syntax

````
typedef enum _DOT11_WPS_CONFIG_METHOD { 
  DOT11_WPS_CONFIG_METHOD_NULL        = 0,
  DOT11_WPS_CONFIG_METHOD_DISPLAY     = 0x0008,
  DOT11_WPS_CONFIG_METHOD_PUSHBUTTON  = 0x0080,
  DOT11_WPS_CONFIG_METHOD_KEYPAD      = 0x0100
} DOT11_WPS_CONFIG_METHOD;
````


## -enum-fields

### -field DOT11_WPS_CONFIG_METHOD_NULL

No setup method is configured.


### -field DOT11_WPS_CONFIG_METHOD_DISPLAY

Setup is configured by a software user interface.


### -field DOT11_WPS_CONFIG_METHOD_PUSHBUTTON

Setup is configured by push button enablement.


### -field DOT11_WPS_CONFIG_METHOD_KEYPAD

Setup is configured by a keypad action.


## -remarks
