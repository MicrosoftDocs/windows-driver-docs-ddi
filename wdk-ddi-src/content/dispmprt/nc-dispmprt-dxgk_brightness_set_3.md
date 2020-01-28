---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET_3
title: DXGK_BRIGHTNESS_SET_3 (dispmprt.h)
description: DxgkBrightnessSet3 Directs the driver to linearly ramp the brightness from its current brightness level to a target brightness level over a specified length of time.
ms.assetid: 8466303f-b811-43e0-91e2-4322a5f3fa83
ms.date: 10/19/2018
f1_keywords:
 - "dispmprt/DXGK_BRIGHTNESS_SET_3"
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
- apiref
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DXGK_BRIGHTNESS_SET_3
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGK_BRIGHTNESS_SET_3 callback function

## -description

*DxgkBrightnessSet3* Directs the driver to linearly ramp the brightness from its current brightness level to a target brightness level over a specified length of time. A set brightness transition can be interrupted by a new DxgkBrightnessSet3 call. The driver should transition from the current brightness level in the interrupted ramp.

## -prototype

```cpp
//Declaration

DXGK_BRIGHTNESS_SET_3 DxgkBrightnessSet3;

// Definition

NTSTATUS DxgkBrightnessSet3
(
	PVOID Context
	ULONG ChildUid
	PDXGK_BRIGHTNESS_SET_IN pIn
)
{...}

DXGK_BRIGHTNESS_SET_3


```

## -parameters

### -param Context

[in] Context pointer provided when querying the interface.

### -param ChildUid

[in] An integer that uniquely identifies the child device. The display miniport driver's [DxgkDdiQueryChildRelations](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md) function previously provided this identifier to the display port driver.

### -param pIn:

[in] A [DXGK_BRIGHTNESS_SET_IN](../d3dkmdt/ns-d3dkmdt-_dxgk_brightness_set_in.md) structure that contains the input parameters for the set brightness call.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code defined in ntstatus.h.
