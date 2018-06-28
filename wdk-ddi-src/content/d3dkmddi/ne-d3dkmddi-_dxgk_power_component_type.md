---
UID: NE:d3dkmddi._DXGK_POWER_COMPONENT_TYPE
title: "_DXGK_POWER_COMPONENT_TYPE"
author: windows-driver-content
description: Indicates the power component type that is reported by the display miniport driver to the Microsoft DirectX graphics kernel subsystem.
old-location: display\dxgk_power_component_type.htm
old-project: display
ms.assetid: fe732082-5aa1-4265-a76a-bd2e5b733557
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_POWER_COMPONENT_ENGINE, DXGK_POWER_COMPONENT_MAX, DXGK_POWER_COMPONENT_MONITOR, DXGK_POWER_COMPONENT_MONITOR_REFRESH, DXGK_POWER_COMPONENT_OTHER, DXGK_POWER_COMPONENT_TYPE, DXGK_POWER_COMPONENT_TYPE enumeration [Display Devices], _DXGK_POWER_COMPONENT_TYPE, d3dkmddi/DXGK_POWER_COMPONENT_ENGINE, d3dkmddi/DXGK_POWER_COMPONENT_MAX, d3dkmddi/DXGK_POWER_COMPONENT_MONITOR, d3dkmddi/DXGK_POWER_COMPONENT_MONITOR_REFRESH, d3dkmddi/DXGK_POWER_COMPONENT_OTHER, d3dkmddi/DXGK_POWER_COMPONENT_TYPE, display.dxgk_power_component_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
api_name:
-	DXGK_POWER_COMPONENT_TYPE
product:
- Windows
targetos: Windows
req.typenames: DXGK_POWER_COMPONENT_TYPE
---

# _DXGK_POWER_COMPONENT_TYPE enumeration


## -description


Indicates the power component type that is reported by the display miniport driver to the Microsoft DirectX graphics kernel subsystem.


## -enum-fields




### -field DXGK_POWER_COMPONENT_ENGINE

Indicates that the component is a  GPU engine.

<div class="alert"><b>Note</b>  An engine can have only one power component assigned.</div>
<div> </div>

### -field DXGK_POWER_COMPONENT_MONITOR

Indicates a monitor that is connected to a VidPN target and can have its power managed. A typical component of this type is an LCD panel backlight.


### -field DXGK_POWER_COMPONENT_MONITOR_REFRESH

Indicates hardware that scans out from a VidPN source and generates a signal for a VidPN target.

A typical component of this type is a self-refreshing monitor, which can display the last frame even if the frame buffer stops sending data to the monitor. The display miniport driver should report this component type only if all monitors that can be driven from the VidPN source are self-refreshing.


### -field DXGK_POWER_COMPONENT_MEMORY


### -field DXGK_POWER_COMPONENT_MEMORY_REFRESH


### -field DXGK_POWER_COMPONENT_OTHER

Indicates a component for which the idle state is managed entirely by the display miniport driver. The DirectX graphics kernel subsystem passes this information to the <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a>.


### -field DXGK_POWER_COMPONENT_D3_TRANSITION


### -field DXGK_POWER_COMPONENT_SHARED

Indicates that the graphics driver supports shared power components.


### -field DXGK_POWER_COMPONENT_MAX

A maximum value that is used for testing purposes.

