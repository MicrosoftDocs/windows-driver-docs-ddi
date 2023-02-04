---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
tech.root: display
title: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3 structure.
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
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
 - DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
 - DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3
dev_langs:
 - c++
---

## -description

The display miniport driver uses **DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3** to report per-plane flip completion after a Vsync.

## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

### -field FirstFreeFlipQueueLogEntryIndex

The index after the last written entry in the flip queue log buffer.

## -remarks

**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3** is a member of the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](./ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure. It is filled out by the driver to report each plane’s flip completion after a Vsync occurs in the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue). It should be filled out when the display adapter generates an interrupt after a Vsync.

## -see-also

[**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2**](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info2.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](./ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)
