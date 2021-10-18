---
UID: NE:d3d12umddi.D3D12DDI_3DPIPELINELEVEL
title: D3D12DDI_3DPIPELINELEVEL
description: Contains values that identify the pipeline level that the driver supports.
tech.root: display
ms.date: 05/13/2021
keywords: ["D3D12DDI_3DPIPELINELEVEL enumeration"]
ms.keywords: D3D12DDI_3DPIPELINELEVEL, D3D12DDI_3DPIPELINELEVEL,
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_3DPIPELINELEVEL
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - D3D12DDI_3DPIPELINELEVEL
 - d3d12umddi/D3D12DDI_3DPIPELINELEVEL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_3DPIPELINELEVEL
product:
 - Windows
dev_langs:
 - c++
---

# D3D12DDI_3DPIPELINELEVEL enumeration

## -description

Contains values that identify the pipeline level that the driver supports.

## -enum-fields

### -field D3D12DDI_3DPIPELINELEVEL_11_0

The driver supports Direct3D version 11 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_1_0_CORE

Internal.

### -field D3D12DDI_3DPIPELINELEVEL_11_1

The driver supports Direct3D version 11.1 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_12_0

The driver supports Direct3D version 12.0 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_12_1

The driver supports Direct3D version 12.1 pipeline.

### -field D3D12DDI_3DPIPELINELEVEL_12_2

The driver supports Direct3D version 12.2 pipeline.

## -remarks

 Drivers only report the maximum level they support.

## -see-also

[**D3D12DDI_3DPIPELINESUPPORT1_DATA_0081**](ns-d3d12umddi-d3d12ddi_3dpipelinesupport1_data_0081.md)

[**D3D12DDIARG_GETCAPS**](../d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps.md)

[**PFND3DDDI_GETCAPS**](../d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps.md)
