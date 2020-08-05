---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
title: _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 (d3dkmddi.h)
description: Used by new drivers to report per-plane flip completion after a VSYNC.
old-location: display\dxgk_multiplane_overlay_vsync_info2.htm
ms.assetid: CC1371C5-1BAB-458C-BC7F-9844B2BBEA3A
ms.date: 05/27/2020
keywords: ["DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, display.dxgk_multiplane_overlay_vsync_info2
f1_keywords:
 - "d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2"
 - "DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
---

# DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure

## -description

Used by new drivers to report per-plane flip completion after a VSYNC.

## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.  

### -field PresentId

The video present source ID provided during a [**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3) call.

### -field Flags

A [**DXGKCB_NOTIFY_MPO_VSYNC_FLAGS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags) structure containing driver-set flags. These flags are used to determine whether the scheduler should call [**DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT**](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) for this plane.

## -remarks

**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2** is a member of the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data) structure. It is filled out by the driver to report each plane’s flip completion after a VSYNC occurs. It should be filled out when the display adapter generates an interrupt after a VSYNC.

## -see-also

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data)

[**DXGKCB_NOTIFY_MPO_VSYNC_FLAGS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkcb_notify_mpo_vsync_flags)

[**DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT**](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md)

[**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3)
