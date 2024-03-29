---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_FLAGS
title: _DXGK_MULTIPLANE_OVERLAY_FLAGS (d3dkmddi.h)
description: The DXGK_MULTIPLANE_OVERLAY_FLAGS structure identifies a flip operation to be performed on an overlay plane.
old-location: display\dxgk_multiplane_overlay_flags.htm
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_FLAGS structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_FLAGS, DXGK_MULTIPLANE_OVERLAY_FLAGS structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_FLAGS, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_FLAGS, display.dxgk_multiplane_overlay_flags
req.header: d3dkmddi.h
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

# _DXGK_MULTIPLANE_OVERLAY_FLAGS structure


## -description

Identifies a flip operation to be performed on an overlay plane.

## -struct-fields

### -field VerticalFlip

The overlay plane should flip the data vertically, making it appear upside-down.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field HorizontalFlip

The overlay plane should flip the data horizontally, making it appear as a right-to-left mirror image.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A 32-bit value that identifies the type of flip operation to perform.

*PanelFitterPostComposition*

Indicates that the plane is to be stretched using panel fitter hardware. 
This should only be set for plane 0. 

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

