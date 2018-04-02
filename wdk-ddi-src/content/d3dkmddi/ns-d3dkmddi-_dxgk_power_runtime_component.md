---
UID: NS:d3dkmddi._DXGK_POWER_RUNTIME_COMPONENT
title: "_DXGK_POWER_RUNTIME_COMPONENT"
author: windows-driver-content
description: Describes information about a power component&#8212;for example, a graphics processing engine, a display device, or a block of memory.
old-location: display\dxgk_power_runtime_component.htm
old-project: display
ms.assetid: ed7e6fc4-651d-4dc3-9c90-cca3c5f0eb67
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_POWER_RUNTIME_COMPONENT, DXGK_POWER_RUNTIME_COMPONENT structure [Display Devices], _DXGK_POWER_RUNTIME_COMPONENT, d3dkmddi/DXGK_POWER_RUNTIME_COMPONENT, display.dxgk_power_runtime_component
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
-	DXGK_POWER_RUNTIME_COMPONENT
product: Windows
targetos: Windows
req.typenames: DXGK_POWER_RUNTIME_COMPONENT
---

# _DXGK_POWER_RUNTIME_COMPONENT structure


## -description


Describes information about a <i>power component</i>—for example, a graphics processing engine, a display device, or a block of memory.


## -struct-fields




### -field StateCount

Defines the number of idle states (F-states) for the power component.


### -field States

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464076">DXGK_POWER_RUNTIME_STATE</a> structure that defines information about every idle state. 

<b>DXGK_MAX_F_STATES</b> is the maximum number of F-states that a power component can have. In Windows 8, <b>DXGK_MAX_F_STATES</b> is defined to have a value of 8.


### -field ComponentMapping

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464067">DXGK_POWER_COMPONENT_MAPPING</a> structure that defines the standard component types of the DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.


### -field Flags

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh464063">DXGK_POWER_COMPONENT_FLAGS</a> structure that specifies power state transition information.


### -field ComponentGuid

A GUID that identifies the power component. This GUID is used by the Power Engine Plug-in (PEP).


### -field ComponentName

A name for the power component. This name is used by GPU profiling tools and is not passed to the PEP.


### -field ProviderCount

Defines the number of other power components that need to be active before this power component becomes active.


### -field Providers

Specifies the indices of other power components that need to be active before this power component becomes active. Each index value must be less than the total number of power components.


## -remarks



Each power component must be mapped to an engine, a display, a memory segment, or another similar device component. The DirectX graphics kernel subsystem detects the idle state of engines, displays, and memory segments.

<div class="alert"><b>Note</b>  Memory segments were removed from Windows 8 but are available in Windows 8.1 and later.</div>
<div> </div>
Multiple power components should not be mapped to the same engine (node), to the same memory segment, or to the same VidPN source or target. A power component can be used with only one engine, memory segment, or VidPN source.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464063">DXGK_POWER_COMPONENT_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464067">DXGK_POWER_COMPONENT_MAPPING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464076">DXGK_POWER_RUNTIME_STATE</a>
 

 

