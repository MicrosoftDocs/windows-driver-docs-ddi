---
UID: NE:dot11wdi._WDI_INTERCONNECT_TYPE
title: _WDI_INTERCONNECT_TYPE
author: windows-driver-content
description: The WDI_INTERCONNECT_TYPE enumeration defines the interconnect types.
old-location: netvista\wdi_interconnect_type.htm
old-project: netvista
ms.assetid: 58cb1ead-94a1-4587-bb2a-7b8e23f42eeb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_INTERCONNECT_TYPE, WDI_INTERCONNECT_TYPE
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
req.alt-api: WDI_INTERCONNECT_TYPE
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
req.typenames: WDI_INTERCONNECT_TYPE
---

# _WDI_INTERCONNECT_TYPE enumeration



## -description
The WDI_INTERCONNECT_TYPE enumeration defines the interconnect types.



## -syntax

````
typedef enum _WDI_INTERCONNECT_TYPE { 
  WDI_INTERCONNECT_MEMORY_MAPPED  = 0,
  WDI_INTERCONNECT_MESSAGE_BASED  = 1,
  WDI_INTERCONNECT_UNKNOWN        = 0xFF
} WDI_INTERCONNECT_TYPE;
````


## -enum-fields

### -field WDI_INTERCONNECT_MEMORY_MAPPED

Target can access system memory (for example, PCI-based interconnect).


### -field WDI_INTERCONNECT_MESSAGE_BASED

Message based interconnect (for example, USB or SDIO).


### -field WDI_INTERCONNECT_UNKNOWN

Unspecified interconnect type.


## -remarks
