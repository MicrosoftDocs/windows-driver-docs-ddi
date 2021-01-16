---
UID: NS:d3dkmddi._DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
title: _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL (d3dkmddi.h)
description: Contains information about the power level of a context.
ms.date: 10/19/2018
keywords: ["DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL structure"]
ms.keywords: _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL, DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL, *INOUT_PDXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
 - d3dkmddi/_DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
 - DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
 - d3dkmddi/DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
 - DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL
dev_langs:
 - c++
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

