---
UID: NC:dispmprt.DXGK_BRIGHTNESS_GET_CAPS_3
title: DXGK_BRIGHTNESS_GET_CAPS_3
author: windows-driver-content
description: Implemented by the client driver to retrieve the brightness control capabilities of an integrated display panel.
ms.assetid: 8611cbe1-4c56-4c39-b2a7-41c73262052b
ms.date:
ms.topic: callback
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
-	DXGK_BRIGHTNESS_GET_CAPS_3
product: 
- Windows
targetos: Windows
---

# DXGK_BRIGHTNESS_GET_CAPS_3 callback function

## -description

Implemented by the client driver to retrieve the brightness control capabilities of an integrated display panel.

## -prototype

```cpp
//Declaration

DXGK_BRIGHTNESS_GET_CAPS_3 DxgkBrightnessGetCaps3;

// Definition

NTSTATUS DxgkBrightnessGetCaps3
(
	PVOID Context
	ULONG ChildUid
	DXGK_BRIGHTNESS_CAPS *pBrightnessCaps
)
{...}

DXGK_BRIGHTNESS_GET_CAPS_3


```

## -parameters

### -param Context

[in] A handle to a context block that is associated with a display adapter.

### -param ChildUid

[in] An integer that uniquely identifies the child device. The display miniport driver's [DxgkDdiQueryChildRelations](..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md) function previously provided this identifier to the display port driver.

### -param *pBrightnessCaps:

[out] Pointer to a [DXGK_BRIGHTNESS_CAPS](..\d3dkmdt\ns-d3dkmdt-_dxgk_brightness_caps.md) structure that represents the brightness control capabilities of the display panel.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code defined in ntstatus.h.

## -remarks

Any device supporting the Brightness3 interface must support transition times, so SmoothBrightness is no longer used.

The NitsBrightness bit has been introduced to represent support for calibrated nit-based brightness. If the device does not support nit-based brightness, brightness levels will still be represented in millinits, but the operating system will be aware that they don’t map to known absolute brightness levels.
