---
UID: NS:d3d12umddi.D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
tech.root: display
title: D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108 structure.
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
req.typenames: D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
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
 - D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
f1_keywords:
 - D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
 - d3d12umddi/D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108
---

# D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108** structure describes a raytracing pipeline to set when the **Type** field of a [**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md) structure is **D3D12DDI_PROGRAM_TYPE_RAYTRACING_PIPELINE_0108**.

## -struct-fields

### -field ProgramIdentifier

A [**D3D12DDI_PROGRAM_IDENTIFIER_0108**](ns-d3d12umddi-d3d12ddi_program_identifier_0108.md) structure that identifies the program to set.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md)  

[**PFND3D12DDI_SET_PROGRAM_0108**](nc-d3d12umddi-pfnd3d12ddi_set_program_0108.md)  
