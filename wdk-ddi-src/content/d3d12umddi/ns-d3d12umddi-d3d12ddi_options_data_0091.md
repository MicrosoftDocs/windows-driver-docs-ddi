---
UID: NS:d3d12umddi.D3D12DDI_OPTIONS_0091
tech.root: display
title: D3D12DDI_OPTIONS_DATA_0091
ms.date: 03/31/2023
targetos: Windows
description: Learn more about the D3D12DDI_OPTIONS_DATA_0091 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_OPTIONS_DATA_0091
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_OPTIONS_0091
 - D3D12DDI_OPTIONS_DATA_0091
f1_keywords:
 - D3D12DDI_OPTIONS_0091
 - d3d12umddi/D3D12DDI_OPTIONS_0091
 - D3D12DDI_OPTIONS_DATA_0091
 - d3d12umddi/D3D12DDI_OPTIONS_DATA_0091
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_OPTIONS_0091
---

## -description

A kernel-mode driver indicates support for capabilities in the **D3D12DDI_OPTIONS_DATA_0091** structure when its [**GetCaps**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) function is called with [**D3D12DDICAPS_TYPE_OPTIONS_0091**](ne-d3d12umddi-d3d12ddicaps_type.md) starting in D3D12DDI_BUILD_VERSION_0091.

## -struct-fields

### -field UnrestrictedBufferTextureCopyPitchSupported

Set TRUE when the driver supports unrestricted copy alignments. Otherwise, set to FALSE.

### -field UnrestrictedVertexElementAlignmentSupported

Set TRUE when the driver supports unrestricted vertex element alignment (potentially unaligned input element layouts). Otherwise, set to FALSE.

### -field InvertedViewportHeightFlipsYSupported

Set TRUE when the driver supports inverted viewports. Otherwise, set to FALSE.

### -field InvertedViewportDepthFlipsZSupported

Set TRUE when the driver supports inverted viewport. Otherwise, set to FALSE.

## -see-also

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**GetCaps**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
