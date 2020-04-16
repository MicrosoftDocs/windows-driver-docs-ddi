---
UID: NS:d3dkmddi._DXGK_POWER_COMPONENT_MAPPING
title: _DXGK_POWER_COMPONENT_MAPPING (d3dkmddi.h)
description: Used in the DXGK_POWER_RUNTIME_COMPONENT.ComponentMapping member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.
old-location: display\dxgk_power_component_mapping.htm
ms.assetid: 6aa00a36-f7a2-4e49-bbd9-1a1ae3592951
ms.date: 05/10/2018
keywords: ["_DXGK_POWER_COMPONENT_MAPPING structure"]
ms.keywords: DXGK_POWER_COMPONENT_MAPPING, DXGK_POWER_COMPONENT_MAPPING structure [Display Devices], _DXGK_POWER_COMPONENT_MAPPING, d3dkmddi/DXGK_POWER_COMPONENT_MAPPING, display.dxgk_power_component_mapping
f1_keywords:
 - "d3dkmddi/DXGK_POWER_COMPONENT_MAPPING"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGK_POWER_COMPONENT_MAPPING
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_POWER_COMPONENT_MAPPING
---

# _DXGK_POWER_COMPONENT_MAPPING structure


## -description


Used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component">DXGK_POWER_RUNTIME_COMPONENT</a>.<b>ComponentMapping</b> member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.


## -struct-fields




### -field ComponentType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_power_component_type">DXGK_POWER_COMPONENT_TYPE</a>-typed value that indicates the power component type that is reported by the display miniport driver to the DirectX graphics kernel subsystem.


### -field EngineDesc

Information about the engine.

### -field EngineDesc.NodeIndex

The index of the engine (node).


### -field MonitorRefreshDesc

Information about the monitor refresh.

### -field MonitorRefreshDesc.VidPnSourceID

An identifier of one of the video present sources associated with the video present network object.


### -field MonitorDesc

Information about the monitor.

### -field MonitorDesc.VidPnTargetID

An identifier of one of the video present targets associated with the VidPN object.


### -field MemoryDesc

Information about the memory.


### -field MemoryDesc.SegmentID

Memory segment ID.

### -field SharedDesc

Shared power component description.

### -field SharedDesc.SharedTypeFlag

Flag that indicates the shared type.

### -field SharedDesc.DriverCustomValueSet

Custom shared value.

### -field SharedDesc.SharedType

Shared type.

## -remarks

Each component must be mapped to an engine, display, memory or other. Dxgkrnl will detect the idle state for engines, displays and memory segments.

* Multiple power components should not be mapped to the same engine (node).
* Multiple power components should not to be mapped to the same memory segment.
* Multiple power components should not be mapped to the same VidPn Source or Target.
* The same power component can be used with only one engine, memory segment or VidPnSourceId.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_power_component_type">DXGK_POWER_COMPONENT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_power_runtime_component">DXGK_POWER_RUNTIME_COMPONENT</a>
 

 

