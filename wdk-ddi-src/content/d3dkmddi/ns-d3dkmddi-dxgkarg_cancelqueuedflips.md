---
UID: NS:d3dkmddi._DXGKARG_CANCELQUEUEDFLIPS
tech.root: display
title: DXGKARG_CANCELQUEUEDFLIPS
ms.date: 02/06/2023
targetos: Windows
description: Learn more about the DXGKARG_CANCELQUEUEDFLIPS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows Server 2022 (WDDM 2.9)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CANCELQUEUEDFLIPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CANCELQUEUEDFLIPS
 - DXGKARG_CANCELQUEUEDFLIPS
f1_keywords:
 - _DXGKARG_CANCELQUEUEDFLIPS
 - d3dkmddi/_DXGKARG_CANCELQUEUEDFLIPS
 - DXGKARG_CANCELQUEUEDFLIPS
 - d3dkmddi/DXGKARG_CANCELQUEUEDFLIPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CANCELQUEUEDFLIPS
---

## -description

The **DXGKARG_CANCELQUEUEDFLIPS** structure contains parameters for the driver's [**DXGKDDI_CANCELQUEUEDFLIPS**](nc-d3dkmddi-dxgkddi_cancelqueuedflips.md) callback function. This structure was superseded by [**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md) starting in WDDM 3.0.

## -struct-fields

### -field VidPnSourceId

[in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source ID of the flip queue.

### -field LayerIndex

[in] Identifies the MPO plane index in the flip queue.

### -field PresentIdCancelRequested

[in] Identifies the range of PresentIds to cancel. This value is the first flip in the range of [**PresentIdCancelRequested**, *LastSubmittedPresentIdToDriver*] flips to be cancelled.

### -field PresentIdCancelled

[out] Specifies the range of PresentIds that the driver synchronously cancelled. This value is the first flip in the range of [**PresentIdCancelled**, *LastSubmittedPresentIdToDriver*] flips that were cancelled. Possible values for **PresentIdCancelled** follow.

| Value | Meaning |
| ----- | ------- |
| **PresentIdCancelRequested** | The driver cancelled all pending flips in the specified range. |
| Greater than or equal to **PresentIdCancelRequested** | The driver couldn't cancel one or more of the pending presents in the specified range. |
| Zero | None of the pending presents were synchronously cancelled. |

## -remarks

Asynchronously cancelled PresentIds are reported via the [VSync interrupt mechanism](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior).

## -see-also

[**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md)
