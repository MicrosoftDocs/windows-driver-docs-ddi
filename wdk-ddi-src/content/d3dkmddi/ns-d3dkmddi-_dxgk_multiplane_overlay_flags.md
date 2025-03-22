---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_FLAGS
title: DXGK_MULTIPLANE_OVERLAY_FLAGS (d3dkmddi.h)
description: Learn more about the DXGK_MULTIPLANE_OVERLAY_FLAGS structure.
ms.date: 05/20/2024
keywords: ["DXGK_MULTIPLANE_OVERLAY_FLAGS structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_FLAGS, DXGK_MULTIPLANE_OVERLAY_FLAGS structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_FLAGS, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_FLAGS, display.dxgk_multiplane_overlay_flags
req.header: d3dkmddi.h
req.construct-type: structure
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_FLAGS
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_FLAGS
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_FLAGS
 - DXGK_MULTIPLANE_OVERLAY_FLAGS
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGK_MULTIPLANE_OVERLAY_FLAGS
 - DXGK_MULTIPLANE_OVERLAY_FLAGS
---

# DXGK_MULTIPLANE_OVERLAY_FLAGS structure (d3dkmddi.h)



## -description

The **DXGK_MULTIPLANE_OVERLAY_FLAGS** structure defines flags that control the behavior of a multiplane overlay operation.

## -struct-fields

### -field VerticalFlip

The overlay plane should flip the data vertically, making it appear upside-down.

### -field HorizontalFlip

The overlay plane should flip the data horizontally, making it appear as a right-to-left mirror image.

### -field StaticCheck

The overlay plane can be scanned out directly. **StaticCheck** is a capability query that doesn't affect the current presentation state. Added in Windows 11 (WDDM 3.0).

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

Represents the collective value of the flags and can be used when the individual bits don't need to be accessed separately.

## -see-also

[**DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES**](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md)

[**DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2**](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2.md)

[**DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3**](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes3.md)
