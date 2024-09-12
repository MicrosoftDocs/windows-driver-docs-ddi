---
UID: NS:d3dkmthk.D3DKMT_MULTIPLANE_OVERLAY
title: D3DKMT_MULTIPLANE_OVERLAY (d3dkmthk.h)
description: Learn more about the D3DKMT_MULTIPLANE_OVERLAY structure.
ms.date: 07/17/2024
keywords: ["D3DKMT_MULTIPLANE_OVERLAY structure"]
ms.keywords: D3DKMT_MULTIPLANE_OVERLAY, D3DKMT_MULTIPLANE_OVERLAY,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_MULTIPLANE_OVERLAY
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - D3DKMT_MULTIPLANE_OVERLAY
 - d3dkmthk/D3DKMT_MULTIPLANE_OVERLAY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_MULTIPLANE_OVERLAY
dev_langs:
 - c++
---

# D3DKMT_MULTIPLANE_OVERLAY structure

## -description

The **D3DKMT_MULTIPLANE_OVERLAY** structure contains information that is used to define a multiplane overlay.

## -struct-fields

### -field LayerIndex

The layer index.

### -field Enabled

Boolean value that specifies whether the overlay is enabled for display.

### -field hAllocation

A handle to a device allocation.

### -field PlaneAttributes

A [**D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES**](ns-d3dkmthk-d3dkmt_multiplane_overlay_attributes.md) structure that contains the plane's attributes.

## -remarks

## -see-also
