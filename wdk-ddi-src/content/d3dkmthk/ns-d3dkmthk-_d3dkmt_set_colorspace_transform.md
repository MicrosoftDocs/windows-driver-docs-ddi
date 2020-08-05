---
UID: NS:d3dkmthk._D3DKMT_SET_COLORSPACE_TRANSFORM
title: _D3DKMT_SET_COLORSPACE_TRANSFORM (d3dkmthk.h)
description: Used to set the color space transform.
old-location: display\d3dkmt-set-colorspace-transform.htm
ms.assetid: 253c689d-ce30-4065-920a-030e3e9f3b8e
ms.date: 05/10/2018
keywords: ["D3DKMT_SET_COLORSPACE_TRANSFORM structure"]
ms.keywords: D3DKMT_SET_COLORSPACE_TRANSFORM, D3DKMT_SET_COLORSPACE_TRANSFORM structure [Display Devices], _D3DKMT_SET_COLORSPACE_TRANSFORM, d3dkmthk/D3DKMT_SET_COLORSPACE_TRANSFORM, display.d3dkmt-set-colorspace-transform
f1_keywords:
 - "d3dkmthk/D3DKMT_SET_COLORSPACE_TRANSFORM"
 - "D3DKMT_SET_COLORSPACE_TRANSFORM"
req.header: d3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMT_SET_COLORSPACE_TRANSFORM
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SET_COLORSPACE_TRANSFORM
---

# _D3DKMT_SET_COLORSPACE_TRANSFORM structure


## -description

Used to set the color space transform.

## -struct-fields

### -field AdapterLuid

A LUID that serves as an identifier for the device. 

### -field VidPnTargetId

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. 

### -field Type

The type of color space.

### -field Size

The size of the color space transform.

### -field pColorSpaceTransform

Pointer to a [D3DKMDT_3x4_COLORSPACE_TRANSFORM](../d3dukmdt/ns-d3dukmdt-_d3dkmdt_3x4_colorspace_transform.md) structure.
