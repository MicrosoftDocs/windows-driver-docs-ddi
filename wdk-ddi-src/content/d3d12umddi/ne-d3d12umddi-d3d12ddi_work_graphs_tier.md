---
UID: NE:d3d12umddi.D3D12DDI_WORK_GRAPHS_TIER
tech.root: display
title: D3D12DDI_WORK_GRAPHS_TIER
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_WORK_GRAPHS_TIER enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2) 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_WORK_GRAPHS_TIER
f1_keywords:
 - D3D12DDI_WORK_GRAPHS_TIER
 - d3d12umddi/D3D12DDI_WORK_GRAPHS_TIER
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WORK_GRAPHS_TIER
---

## -description

The **D3D12DDI_WORK_GRAPHS_TIER** enumeration specifies the work graphs tier supported by the driver.

## -enum-fields

### -field D3D12DDI_WORK_GRAPHS_TIER_NOT_SUPPORTED

The driver doesn't support work graphs.

### -field D3D12DDI_WORK_GRAPHS_TIER_0_1

The driver supports the first experimental work graphs release.

### -field D3D12DDI_WORK_GRAPHS_TIER_1_0

The driver fully supports the first full work graphs release.

## -remarks

For more information about work graphs, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_OPTIONS_DATA_0103**](ns-d3d12umddi-d3d12ddi_options_data_0103.md)

[**D3D12DDICAPS_TYPE**](ne-d3d12umddi-d3d12ddicaps_type.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
