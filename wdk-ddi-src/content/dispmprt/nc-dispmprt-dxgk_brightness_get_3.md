---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_3
title: DXGK_BRIGHTNESS_GET_3
author: windows-driver-content
description: Implemented by the client driver to retrieve the currently active brightness level of an integrated display panel, with details on the brightness transition in progress.
ms.assetid: 0bcf8d16-da3a-45a3-b9cc-d767b69695db
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
-	DXGK_BRIGHTNESS_GET_3
product: 
- Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_GET_3 callback function

## -description

Implemented by the client driver to retrieve the currently active brightness level of an integrated display panel, with details on the brightness transition in progress.

## -prototype

```cpp
//Declaration

DXGK_BRIGHTNESS_GET_3 DxgkBrightnessGet3;

// Definition

NTSTATUS DxgkBrightnessGet3
(
	PVOID Context
	ULONG ChildUid
	PDXGK_BRIGHTNESS_GET_OUT pOut
)
{...}

DXGK_BRIGHTNESS_GET_3


```

## -parameters

### -param Context

[in] A handle to a context block that is associated with a display adapter.

### -param ChildUid

[in] An integer that uniquely identifies the child device. The display miniport driver's [DxgkDdiQueryChildRelations](..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md) function previously provided this identifier to the display port driver.

### -param pOut

[out] Pointer to a [PDXGK_BRIGHTNESS_GET_OUT](..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_get_out.md) structure that contains the output parameters for the get brightness call.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code defined in ntstatus.h.


