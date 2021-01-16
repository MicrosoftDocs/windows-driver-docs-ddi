---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
title: _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS (d3dkmddi.h)
description: A structure containing the flags set by the driver to process a flip entry.
old-location: display\dxgkcb_notify_mpo_vsync_flags.htm
ms.date: 05/10/2018
keywords: ["DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure"]
ms.keywords: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure [Display Devices], _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, d3dkmddi/DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, display.dxgkcb_notify_mpo_vsync_flags
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

# _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure


## -description

A structure containing the flags set by the driver to process a flip entry.

## -struct-fields

### -field PostPresentNeeded

The driver sets this flag to indicate that scheduler must call [DxgkDdiPostMultiplaneOverlayPresent](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) for this flip entry.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

