---
UID: NE:windot11._DOT11_POWER_MODE_REASON
title: _DOT11_POWER_MODE_REASON
author: windows-driver-content
description: The DOT11_POWER_MODE_REASON lists the different reasons for changes to auto power save mode state.
old-location: netvista\dot11_power_mode_reason.htm
old-project: netvista
ms.assetid: 0B8402B5-CFDA-402F-BA7A-A44478333C04
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_POWER_MODE_REASON, DOT11_POWER_MODE_REASON
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
req.alt-api: DOT11_POWER_MODE_REASON
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
req.typenames: DOT11_POWER_MODE_REASON
req.product: Windows 10 or later.
---

# _DOT11_POWER_MODE_REASON enumeration



## -description

## -syntax

````
typedef enum _DOT11_POWER_MODE_REASON { 
  dot11_power_mode_reason_no_change             = 0,
  dot11_power_mode_reason_noncompliant_AP       = 1,
  dot11_power_mode_reason_legacy_WFD_device     = 2,
  dot11_power_mode_reason_compliant_AP          = 3,
  dot11_power_mode_reason_compliant_WFD_device  = 4,
  dot11_power_mode_reason_others                = 5
} DOT11_POWER_MODE_REASON;
````


## -enum-fields

### -field dot11_power_mode_reason_no_change

Device is initially in this state and has not changed since.


### -field dot11_power_mode_reason_noncompliant_AP

AP is not compliant. As to be in CAM.


### -field dot11_power_mode_reason_legacy_WFD_device

WFD device is legacy.


### -field dot11_power_mode_reason_compliant_AP

AP is compliant.


### -field dot11_power_mode_reason_compliant_WFD_device

All connected WFD device can do PSM.


### -field dot11_power_mode_reason_others

Other reason.


## -remarks
