---
UID: NS:d3dkmddi._DXGK_POWER_RUNTIME_STATE
title: _DXGK_POWER_RUNTIME_STATE (d3dkmddi.h)
description: Describes the characteristics of an idle state (an F-state).
old-location: display\dxgk_power_runtime_state.htm
ms.assetid: f2bfb07c-1493-4a29-9d42-e284af29a376
ms.date: 05/10/2018
keywords: ["DXGK_POWER_RUNTIME_STATE structure"]
ms.keywords: DXGK_POWER_RUNTIME_STATE, DXGK_POWER_RUNTIME_STATE structure [Display Devices], _DXGK_POWER_RUNTIME_STATE, d3dkmddi/DXGK_POWER_RUNTIME_STATE, display.dxgk_power_runtime_state
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
targetos: Windows
tech.root: display
req.typenames: DXGK_POWER_RUNTIME_STATE
f1_keywords:
 - _DXGK_POWER_RUNTIME_STATE
 - d3dkmddi/_DXGK_POWER_RUNTIME_STATE
 - DXGK_POWER_RUNTIME_STATE
 - d3dkmddi/DXGK_POWER_RUNTIME_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGK_POWER_RUNTIME_STATE
---

# _DXGK_POWER_RUNTIME_STATE structure


## -description

Describes the characteristics of an idle state (an F-state).

## -struct-fields

### -field TransitionLatency

The amount of time, in 100-nanosecond units, that the component takes to return to the F0 state.
   This value should be zero for the F0 state.

### -field ResidencyRequirement

The minimal amount of time, in 100-nanosecond units, that is required to spend in
   this F-state to make it worthwhile. This value should be zero for the F0 state.

### -field NominalPower

The power draw, in microwatt units, of the component in this F-state. This  value should not be zero for the F0 state.

## -remarks

F-states in hardware must be defined such that a deeper F-state (higher F-value) will use less power and take longer to return to the latent F0 state.

