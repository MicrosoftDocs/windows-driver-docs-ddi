---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
title: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 (d3dkmddi.h)
description: Learn more about the DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 function.
ms.date: 02/03/2023
keywords: ["DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure"]
ms.keywords: "*IN_OUT_PDXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure [Display Devices], _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3, display.dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
f1_keywords:
 - _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
 - d3dkmddi/_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
 - DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
 - d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
 - DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3
---

# DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3 structure

## -description

**DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3** contains arguments for the [**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) function.

## -struct-fields

### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.

### -field InputFlags

A [**DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS**](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_input_flags.md) structure that identifies the type of display operation to perform.

### -field OutputFlags

A [**DXGK_SETVIPNSOURCEADDRESS_OUTPUT_FLAGS**](ns-d3dkmddi-_dxgk_setvidpnsourceaddress_output_flags.md) structure that returns information from the driver.

### -field PlaneCount

The number of overlay planes in the **ppPlanes** list.

### -field ppPlanes

An array of pointers to a [**DXGK_MULTIPLANE_OVERLAY_PLANE3**](ns-d3dkmddi-_dxgk_multiplane_overlay_plane3.md) structures that specify the overlay planes to display.

### -field pPostComposition

Pointer to a [**DXGK_MULTIPLANE_OVERLAY_POST_COMPOSITION**](ns-d3dkmddi-_dxgk_multiplane_overlay_post_composition.md) structure containing virtual mode information and other transform information that should be applied after the planes have been composed.

If NULL, no post composition transforms should be applied.

### -field Duration

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.

### -field pHDRMetaData

Pointer to a [**DXGK_HDR_METADATA**](ns-d3dkmddi-_dxgk_hdr_metadata.md) structure indicating any metadata information that might be available. A NULL value indicates that no new metadata is available.

### -field TargetFlipTime

Value that describes the target flip time in QPC units. When the clock reaches this value, the frame is allowed to be sent to the display while honoring VSync and tearing flags. See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

## -see-also

[**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md)
