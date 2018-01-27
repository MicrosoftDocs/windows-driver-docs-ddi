---
UID: NE:wditypes._WDI_POWER_SAVE_LEVEL
title: _WDI_POWER_SAVE_LEVEL
author: windows-driver-content
description: The WDI_POWER_SAVE_LEVEL enumeration defines the power save levels.
old-location: netvista\wdi_power_save_level.htm
old-project: netvista
ms.assetid: 3CB311C1-8FAE-44D5-896D-972F5DF1E88A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wditypes/WDI_POWER_SAVE_LEVEL_MAX_PSP, WDI_POWER_SAVE_LEVEL enumeration [Network Drivers Starting with Windows Vista], _WDI_POWER_SAVE_LEVEL, wditypes/WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE, netvista.wdi_power_save_level, WDI_POWER_SAVE_LEVEL_FAST_PSP, netvista.wifi_power_save_level, wditypes/WDI_POWER_SAVE_LEVEL, wditypes/WDI_POWER_SAVE_LEVEL_FAST_PSP, WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL, WDI_POWER_SAVE_LEVEL, wditypes/WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL, WDI_POWER_SAVE_LEVEL_MAX_PSP, WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname: 
-	WDI_POWER_SAVE_LEVEL
product: Windows
targetos: Windows
req.typenames: WDI_POWER_SAVE_LEVEL
req.product: Windows 10 or later.
---

# _WDI_POWER_SAVE_LEVEL enumeration


## -description


The WDI_POWER_SAVE_LEVEL enumeration defines the power save levels.


## -syntax


````
typedef enum _WDI_POWER_SAVE_LEVEL { 
  WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE  = 0,
  WDI_POWER_SAVE_LEVEL_FAST_PSP       = 8,
  WDI_POWER_SAVE_LEVEL_MAX_PSP        = 16,
  WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL  = 24
} WDI_POWER_SAVE_LEVEL;
````


## -enum-fields




### -field WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE

No power saving.


### -field WDI_POWER_SAVE_LEVEL_FAST_PSP

Fast PSP.


### -field WDI_POWER_SAVE_LEVEL_MAX_PSP

Maximum PSP.


### -field WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL

Maximum power saving level.

