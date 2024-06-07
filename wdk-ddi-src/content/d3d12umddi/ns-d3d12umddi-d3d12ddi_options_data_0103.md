---
UID: NS:d3d12umddi.D3D12DDI_OPTIONS1_DATA_0103
tech.root: display
title: D3D12DDI_OPTIONS_DATA_0103
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_OPTIONS_DATA_0103 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_OPTIONS_DATA_0103
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
 - D3D12DDI_OPTIONS1_DATA_0103
 - D3D12DDI_OPTIONS_DATA_0103
f1_keywords:
 - D3D12DDI_OPTIONS1_DATA_0103
 - d3d12umddi/D3D12DDI_OPTIONS1_DATA_0103
 - D3D12DDI_OPTIONS_DATA_0103
 - d3d12umddi/D3D12DDI_OPTIONS_DATA_0103
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_OPTIONS1_DATA_0103
---

## -description

A user-mode driver indicates support for capabilities in the **D3D12DDI_OPTIONS_DATA_0103** structure when its [**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md) function is called with [**D3D12DDICAPS_TYPE_OPTIONS_0103**](ne-d3d12umddi-d3d12ddicaps_type.md).

## -struct-fields

### -field WorkGraphsTier

A [**D3D12DDI_WORK_GRAPHS_TIER**](ne-d3d12umddi-d3d12ddi_work_graphs_tier.md) enumeration that specifies the work graphs tier supported by the driver. For more information about work graphs, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
