---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
title: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 (d3dkmddi.h)
description: Used by new drivers to report per-plane flip completion after a VSYNC.
old-location: display\dxgk_multiplane_overlay_vsync_info2.htm
ms.date: 10/13/2021
keywords: ["DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, display.dxgk_multiplane_overlay_vsync_info2
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607 (WDDM 2.1)
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
 - DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
 - DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
---

# DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure

## -description

The **DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2** structure is used by display miniport drivers to report per-plane flip completion after a VSYNC.

## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

### -field PresentId

The video present source ID provided during a [**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](./nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) call.

### -field Flags

A [**DXGKCB_NOTIFY_MPO_VSYNC_FLAGS**](./ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags.md) structure containing driver-set flags. These flags are used to determine whether the scheduler should call [**DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT**](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) for this plane.

## -remarks

**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2** is a member of the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](./ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure. It is filled out by the driver to report each plane’s flip completion after a VSYNC occurs. It should be filled out when the display adapter generates an interrupt after a VSYNC.

## -see-also

[**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3**](ns-d3dkmddi-dxgk_multiplane_overlay_vsync_info3.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](./ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[**DXGKCB_NOTIFY_MPO_VSYNC_FLAGS**](./ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags.md)

[**DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT**](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md)

[**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](./nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md)
