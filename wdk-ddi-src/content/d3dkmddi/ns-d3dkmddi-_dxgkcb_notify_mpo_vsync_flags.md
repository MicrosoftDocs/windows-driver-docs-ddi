---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
title: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS (d3dkmddi.h)
description: A structure containing the flags set by the driver to process a flip entry.
old-location: display\dxgkcb_notify_mpo_vsync_flags.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure"]
ms.keywords: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure [Display Devices], _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, d3dkmddi/DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, display.dxgkcb_notify_mpo_vsync_flags
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
req.typenames: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
f1_keywords:
 - _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
 - d3dkmddi/_DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
 - DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
 - d3dkmddi/DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
 - DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
---

# DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure

## -description

The **DXGKCB_NOTIFY_MPO_VSYNC_FLAGS** structure contains the flags set by the driver to process a flip entry.

## -struct-fields

### -field PostPresentNeeded

The driver sets this flag to indicate that scheduler must call [**DxgkDdiPostMultiplaneOverlayPresent**](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) for this flip entry.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit **Value** member to zeros.

### -field Value

The 32-bit value that indicates all of the flags set in the union.

## -see-also

[**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2**](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info2.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](./ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)
