---
UID: NS:d3dkmddi._DXGKARG_CONTROLMODEBEHAVIOR
title: _DXGKARG_CONTROLMODEBEHAVIOR
description: Arguments used to describe display mode behaviors that the OS requests of the driver and the results of the request.
ms.assetid: 708d7d44-6261-438f-93e7-f12e338e870e
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGKARG_CONTROLMODEBEHAVIOR, DXGKARG_CONTROLMODEBEHAVIOR, *INOUT_PDXGKARG_CONTROLMODEBEHAVIOR
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
req.typenames: DXGKARG_CONTROLMODEBEHAVIOR
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARG_CONTROLMODEBEHAVIOR
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARG_CONTROLMODEBEHAVIOR structure

## -description

Arguments used to describe display mode behaviors that the OS requests of the driver and the results of the request.

## -struct-fields

### -field Request

Indicates the behaviors that the OS is requesting

### -field Satisfied

Flags that report which requests were satisfied.  Only flags which were set in the Request field and which the driver has been able to apply the requested behavior should be set.

### -field NotSatisfied

Flags that report which requests were not satisfied.  Only flags which were set in the Request field which the driver supports on this adapter but could not be applied should be set.

## -remarks

If a behavior is not supported, then even if the driver comprehends the behavior, it should leave the flag bit clear in both the Satisfied and the NotSatisfied field.

## -see-also

[DXGK_MODE_BEHAVIOR_FLAGS](../d3dkmddi/ns-d3dkmddi-_dxgk_mode_behavior_flags.md)
