---
UID: NE:dot11wdi._WDI_RX_THROTTLE_LEVEL
title: _WDI_RX_THROTTLE_LEVEL
author: windows-driver-content
description: The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).
old-location: netvista\wdi_rx_throttle_level.htm
old-project: netvista
ms.assetid: 637c0892-8d73-45b7-b679-ff3a0ba78a9c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_RX_THROTTLE_LEVEL, WDI_RX_THROTTLE_LEVEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_RX_THROTTLE_LEVEL
req.alt-loc: dot11wdi.h
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
req.typenames: WDI_RX_THROTTLE_LEVEL
---

# _WDI_RX_THROTTLE_LEVEL enumeration



## -description
The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).



## -syntax

````
typedef enum _WDI_RX_THROTTLE_LEVEL { 
  WDI_RxThrottleLevelNone        = 0x0,
  WDI_RxThrottleLevelMedium      = 0x1,
  WDI_RxThrottleLevelAggressive  = 0x2
} WDI_RX_THROTTLE_LEVEL;
````


## -enum-fields

### -field WDI_RxThrottleLevelNone

No throttling.


### -field WDI_RxThrottleLevelMedium

Medium throttling.


### -field WDI_RxThrottleLevelAggressive

Aggressive throttling.


## -remarks
