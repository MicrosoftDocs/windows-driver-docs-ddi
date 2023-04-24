---
UID: NS:d3dkmddi._DXGKARG_CANCELFLIPS
tech.root: display
title: DXGKARG_CANCELFLIPS
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKARG_CANCELFLIPS callback function.
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
req.typenames: DXGKARG_CANCELFLIPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CANCELFLIPS
 - DXGKARG_CANCELFLIPS
f1_keywords:
 - _DXGKARG_CANCELFLIPS
 - d3dkmddi/_DXGKARG_CANCELFLIPS
 - DXGKARG_CANCELFLIPS
 - d3dkmddi/DXGKARG_CANCELFLIPS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CANCELFLIPS
---

## -description

The **DXGKARG_CANCELFLIPS** structure contains parameters for the driver's [**DXGKDDI_CANCELFLIPS**](nc-d3dkmddi-dxgkddi_cancelflips.md) callback function.

## -struct-fields

### -field VidPnSourceId

[in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source ID of the flip queue.

### -field PlaneCount

[in] Number of planes with pending Presents to cancel; that is, the number of [**DXGK_CANCELFLIPS_PLANE**](ns-d3dkmddi-dxgk_cancelflips_plane.md) structures in the array that **ppPlanes** points to.

### -field ppPlanes

[in/out] Pointer to an array of [**DXGK_CANCELFLIPS_PLANE**](ns-d3dkmddi-dxgk_cancelflips_plane.md) structures, each containing a per plane cancel request.

## -remarks

Asynchronously cancelled PresentIds are reported via the [VSync interrupt mechanism](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior).

See [Cancelling interlocked flips on multiple planes](/windows-hardware/drivers/display/hardware-flip-queue#cancelling-interlocked-flips-on-multiple-planes) for more information.

## -see-also

[**DXGK_CANCELFLIPS_PLANE**](ns-d3dkmddi-dxgk_cancelflips_plane.md)

[**DXGKDDI_CANCELFLIPS**](nc-d3dkmddi-dxgkddi_cancelflips.md)
