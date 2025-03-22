---
UID: NE:d3d12umddi.D3D12DDI_PROGRAM_TYPE_0108
tech.root: display
title: D3D12DDI_PROGRAM_TYPE_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_PROGRAM_TYPE_0108 enumeration.
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
 - D3D12DDI_PROGRAM_TYPE_0108
f1_keywords:
 - D3D12DDI_PROGRAM_TYPE_0108
 - d3d12umddi/D3D12DDI_PROGRAM_TYPE_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_PROGRAM_TYPE_0108
---

# D3D12DDI_PROGRAM_TYPE_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_PROGRAM_TYPE_0108** enumeration specifies the type of program to set on a command list.

## -enum-fields

### -field D3D12DDI_PROGRAM_TYPE_GENERIC_PIPELINE_0108

The program is a generic pipeline that starts with a vertex or mesh shader.

### -field D3D12DDI_PROGRAM_TYPE_RAYTRACING_PIPELINE_0108

The program is a raytracing pipeline. Not currently supported.

### -field D3D12DDI_PROGRAM_TYPE_WORK_GRAPH_0108

The program is a work graph. For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md)

[**PFND3D12DDI_SET_PROGRAM_0108**](nc-d3d12umddi-pfnd3d12ddi_set_program_0108.md)
