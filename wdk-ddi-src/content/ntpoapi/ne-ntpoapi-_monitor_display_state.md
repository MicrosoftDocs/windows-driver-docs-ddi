---
UID: NE:ntpoapi._MONITOR_DISPLAY_STATE
title: "_MONITOR_DISPLAY_STATE"
author: windows-driver-content
description: Indicates the power state of the monitor being displayed on.
old-location: kernel\monitor_display_state.htm
old-project: kernel
ms.assetid: 50F5C1AD-BA51-4376-8093-E8596265FDAF
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PMONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE enumeration [Kernel-Mode Driver Architecture], PowerMonitorDim, PowerMonitorOff, PowerMonitorOn, _MONITOR_DISPLAY_STATE, kernel.monitor_display_state, wdm/MONITOR_DISPLAY_STATE, wdm/PowerMonitorDim, wdm/PowerMonitorOff, wdm/PowerMonitorOn"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntpoapi.h
req.include-header: Ntpoapi.h
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
-	wdm.h
api_name:
-	MONITOR_DISPLAY_STATE
product: Windows
targetos: Windows
req.typenames: MONITOR_DISPLAY_STATE, *PMONITOR_DISPLAY_STATE
---

# _MONITOR_DISPLAY_STATE enumeration


## -description


Indicates the power state of the monitor being displayed on.


## -syntax


````
typedef enum _MONITOR_DISPLAY_STATE { 
  PowerMonitorOff  = 0,
  PowerMonitorOn,
  PowerMonitorDim
} MONITOR_DISPLAY_STATE;
````


## -enum-fields




### -field PowerMonitorOff

This indicates that the monitor is off.


### -field PowerMonitorOn

This indicates that the monitor is on.


### -field PowerMonitorDim

This indicates that the monitor is dim.

