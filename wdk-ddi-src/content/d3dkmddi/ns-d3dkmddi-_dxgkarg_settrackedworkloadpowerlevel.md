---
UID: NS:d3dkmddi._DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
title: _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
author: windows-driver-content
description: Contains information about the power level of a context.
ms.assetid: c8d248e4-3805-4e67-b11e-e5553e7561f8
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL, DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL, *INOUT_PDXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dkmddi.h
api_name: 
-	_DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
product:
-	Windows
targetos: Windows
tech.root: display
---

# _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL structure

## -description

Contains information about the power level of a context.

## -struct-fields

### -field PowerLevel

The power level is an UINT that varies from 0 to 100, where 100 means the maximum power the engine supports.

### -field EffectivePowerLevel

Returns the effective power level that was set on the context by the driver.

### -field Flags
 
A combination of [DXGK_TRACKEDWORKLOAD_STATE_FLAGS](ns-d3dkmddi-_dxgk_trackedworkload_state_flags.md).

## -remarks

## -see-also
