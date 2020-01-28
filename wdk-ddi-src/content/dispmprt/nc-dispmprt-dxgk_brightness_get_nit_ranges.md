---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_NIT_RANGES
title: DXGK_BRIGHTNESS_GET_NIT_RANGES (dispmprt.h)
description: Implemented by the client driver to retrieve a list of supported nit ranges.
ms.assetid: 8c36880d-c3e2-4aac-9904-5abf5cd0e6bc
ms.date: 10/19/2018
f1_keywords:
 - "dispmprt/DXGK_BRIGHTNESS_GET_NIT_RANGES"
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
- DXGK_BRIGHTNESS_GET_NIT_RANGES
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGK_BRIGHTNESS_GET_NIT_RANGES callback function

## -description

Implemented by the client driver to retrieve a list of supported nit ranges.

## -prototype

```cpp
//Declaration

DXGK_BRIGHTNESS_GET_NIT_RANGES DxgkBrightnessGetNitRanges;

// Definition

NTSTATUS DxgkBrightnessGetNitRanges
(
	PVOID Context
	ULONG ChildUid
	PDXGK_BRIGHTNESS_GET_NIT_RANGES_OUT pOut
)
{...}

DXGK_BRIGHTNESS_GET_NIT_RANGES


```

## -parameters

### -param Context

[in] Context pointer provided when querying the interface.

### -param ChildUid

[in] An integer that uniquely identifies the child device. The display miniport driver's [DxgkDdiQueryChildRelations](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md) function previously provided this identifier to the display port driver.

### -param pOut:

[out] A pointer to a [DXGK_BRIGHTNESS_GET_NIT_RANGES_OUT](../d3dkmdt/ns-d3dkmdt-_dxgk_brightness_get_nit_ranges_out.md) structure that represents the supported brightness ranges of the display panel.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code defined in ntstatus.h.

