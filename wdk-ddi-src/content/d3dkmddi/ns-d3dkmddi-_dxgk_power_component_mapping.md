---
UID: NS:d3dkmddi._DXGK_POWER_COMPONENT_MAPPING
title: "_DXGK_POWER_COMPONENT_MAPPING"
author: windows-driver-content
description: Used in the DXGK_POWER_RUNTIME_COMPONENT.ComponentMapping member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.
old-location: display\dxgk_power_component_mapping.htm
old-project: display
ms.assetid: 6aa00a36-f7a2-4e49-bbd9-1a1ae3592951
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_POWER_COMPONENT_MAPPING, DXGK_POWER_COMPONENT_MAPPING structure [Display Devices], _DXGK_POWER_COMPONENT_MAPPING, d3dkmddi/DXGK_POWER_COMPONENT_MAPPING, display.dxgk_power_component_mapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_POWER_COMPONENT_MAPPING
product: Windows
targetos: Windows
req.typenames: DXGK_POWER_COMPONENT_MAPPING
---

# _DXGK_POWER_COMPONENT_MAPPING structure


## -description


Used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464073">DXGK_POWER_RUNTIME_COMPONENT</a>.<b>ComponentMapping</b> member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.


## -struct-fields




### -field ComponentType

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464070">DXGK_POWER_COMPONENT_TYPE</a>-typed value that indicates the power component type that is reported by the display miniport driver to the DirectX graphics kernel subsystem.


### -field EngineDesc


### -field EngineDesc.NodeIndex

The index of the engine (node).


### -field MonitorRefreshDesc


### -field MonitorRefreshDesc.VidPnSourceID

An identifier of one of the video present sources associated with the video present network object.


### -field MonitorDesc


### -field MonitorDesc.VidPnTargetID

An identifier of one of the video present targets associated with the VidPN object.


### -field MemoryDesc

 


### -field MemoryDesc.SegmentID

 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464070">DXGK_POWER_COMPONENT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464073">DXGK_POWER_RUNTIME_COMPONENT</a>
 

 

