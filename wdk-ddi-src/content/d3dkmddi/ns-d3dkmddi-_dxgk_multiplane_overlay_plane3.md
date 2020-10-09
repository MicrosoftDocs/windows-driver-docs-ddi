---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE3
title: _DXGK_MULTIPLANE_OVERLAY_PLANE3 (d3dkmddi.h)
description: Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3 function.
old-location: display\dxgk_multiplane_overlay_plane3.htm
ms.assetid: 2C524702-A819-4B91-B236-E00B2820813C
ms.date: 04/16/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_PLANE3 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE3, DXGK_MULTIPLANE_OVERLAY_PLANE3 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE3, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE3, display.dxgk_multiplane_overlay_plane3
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE3
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE3
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_PLANE3
 - DXGK_MULTIPLANE_OVERLAY_PLANE3
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_MULTIPLANE_OVERLAY_PLANE3
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE3 structure


## -description

Specifies an overlay plane to display in a call to the [DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) function.

## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

### -field PresentId

A 64 bit per-plane identifier used by the driver to report completion of the overlay command.

### -field InputFlags

A [DXGK_PLANE_SPECIFIC_INPUT_FLAGS](ns-d3dkmddi-_dxgk_plane_specific_input_flags.md) structure that identifies any plane specific display operations to perform.

### -field OutputFlags

A [DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS](ns-d3dkmddi-_dxgk_plane_specific_output_flags.md) structure containing status returned by the driver.

### -field MaxImmediateFlipLine

The display line delineating whether a VSYNC flip should be promoted to an immediate flip, where line 0 corresponds to the first active pixel of the frame. This value is ignored for non-VSYNC flips.



This value is -1 when promotion from a VSYNC flip to an immediate flip is not desired. In this case, the flip will always wait for the next VSYNC.

For a value other than -1, the driver should promote this flip to an immediate flip if the HW has not yet started reading from the specified display line. Values of 0 can be promoted to immediate flips if the HW has latched registers for the current display frame but has not yet started scanning the first active pixel.



The display line value is relative to the physical mode that is set. If the display is performing scaling, display line is relative to the size after scaling has been applied.





When a VSYNC flip is promoted to an immediate flip, the driver should set [DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS](ns-d3dkmddi-_dxgk_plane_specific_output_flags.md). FlipConvertedToImmediate to TRUE.

### -field ContextCount

The number of contexts in the array that the Context member specifies.

### -field ppContextData

An array of handles to the contexts that contributed to a display operation.

### -field DriverPrivateDataSize

The size of the private driver data.

### -field pDriverPrivateData

Private driver data.

### -field PlaneAttributes

A structure of type [DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes3.md) that specifies overlay plane attributes.

