---
UID: NS:d3dkmddi._DXGK_CANCELFLIPS_PLANE
tech.root: display
title: DXGK_CANCELFLIPS_PLANE
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGK_CANCELFLIPS_PLANE structure.
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
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_CANCELFLIPS_PLANE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CANCELFLIPS_PLANE
 - DXGK_CANCELFLIPS_PLANE
f1_keywords:
 - _DXGK_CANCELFLIPS_PLANE
 - d3dkmddi/_DXGK_CANCELFLIPS_PLANE
 - DXGK_CANCELFLIPS_PLANE
 - d3dkmddi/DXGK_CANCELFLIPS_PLANE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_CANCELFLIPS_PLANE
---

## -description

In the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue), the **DXGK_CANCELFLIPS_PLANE** structure contains a [plane cancel request](nc-d3dkmddi-dxgkddi_cancelflips.md).

## -struct-fields

### -field PresentIdCancelRequested

[in] Identifies the range of PresentIds to cancel. This value is the first flip in the range of [**PresentIdCancelRequested**, *LastSubmittedPresentIdToDriver*] flips to be cancelled.

### -field PresentIdCancelled

[out] Specifies the range of PresentIds that the driver synchronously cancelled. This value is the first flip in the range of [**PresentIdCancelled**, *LastSubmittedPresentIdToDriver*] flips that were cancelled. Possible values for **PresentIdCancelled** follow.

| Value | Meaning |
| ----- | ------- |
| **PresentIdCancelRequested** | The driver cancelled all pending flips in the specified range. |
| Greater than or equal to **PresentIdCancelRequested** | The driver couldn't cancel one or more of the pending presents in the specified range. |
| Zero | None of the pending presents were synchronously cancelled. |

### -field LayerIndex

[in] Identifies the MPO plane index in the flip queue.

## -remarks

The [**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md) structure contains a pointer to an array of **DXGK_CANCELFLIPS_PLANE** structures, each containing a per plane cancel request.

See [Cancelling interlocked flips on multiple planes](/windows-hardware/drivers/display/hardware-flip-queue#cancelling-interlocked-flips-on-multiple-planes) for more information.

## -see-also

[**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md)

[**DXGKDDI_CANCELFLIPS**](nc-d3dkmddi-dxgkddi_cancelflips.md)
