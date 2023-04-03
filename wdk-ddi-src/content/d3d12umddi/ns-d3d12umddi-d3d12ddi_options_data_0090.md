---
UID: NS:d3d12umddi.D3D12DDI_OPTIONS_0090
tech.root: display
title: D3D12DDI_OPTIONS_DATA_0090
ms.date: 03/31/2023
targetos: Windows
description: Learn more about the D3D12DDI_OPTIONS_DATA_0090 structure.
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
req.typenames: D3D12DDI_OPTIONS_DATA_0090
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
 - D3D12DDI_OPTIONS_0090
 - D3D12DDI_OPTIONS_DATA_0090
f1_keywords:
 - D3D12DDI_OPTIONS_0090
 - d3d12umddi/D3D12DDI_OPTIONS_0090
 - D3D12DDI_OPTIONS_DATA_0090
 - d3d12umddi/D3D12DDI_OPTIONS_DATA_0090
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_OPTIONS_0090
---

## -description

A kernel-mode driver indicates support for capabilities in the **D3D12DDI_OPTIONS_DATA_0090** structure when its [**GetCaps**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) function is called with [**D3D12DDICAPS_TYPE_OPTIONS_0090**](ne-d3d12umddi-d3d12ddicaps_type.md) starting in D3D12DDI_BUILD_VERSION_0090.

## -struct-fields

### -field RelaxedFormatCastingSupported

Set TRUE when the driver supports format list casting; otherwise, set to FALSE.

## -see-also

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**D3DDDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**GetCaps**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)