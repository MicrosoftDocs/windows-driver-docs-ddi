---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
title: DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
author: windows-driver-content
description: Implemented by the client driver to set the level of optimization used to control the brightness of a panel.
ms.assetid: 07bffb8b-08d5-4f24-bdf3-c3a4648e8724
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3
product: 
- Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3 callback function

## -description

Implemented by the client driver to set the level of optimization used to control the brightness of a panel.

## -prototype

```cpp
//Declaration

DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3 DxgkBrightnessSetBacklightOptimization3;

// Definition

NTSTATUS DxgkBrightnessSetBacklightOptimization3
(
	PVOID Context
	ULONG ChildUid
	DXGK_BACKLIGHT_OPTIMIZATION_LEVEL OptimizationLevel
)
{...}

DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION_3


```

## -parameters

### -param Context

[in] Context pointer provided when querying the interface.

### -param ChildUid

[in] An integer that uniquely identifies the child device. The display miniport driver's [DxgkDdiQueryChildRelations](..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md) function previously provided this identifier to the display port driver.

### -param OptimizationLevel

[in] A value of type [DXGK_BACKLIGHT_OPTIMIZATION_LEVEL](..\d3dkmdt\ne-d3dkmdt-dxgk_backlight_optimization_level.md) that indicates the optimization level of brightness control.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code defined in ntstatus.h.
