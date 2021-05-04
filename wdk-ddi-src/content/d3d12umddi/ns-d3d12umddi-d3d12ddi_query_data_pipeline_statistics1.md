---
UID: NS:d3d12umddi.D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
tech.root: display
title: D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
ms.date: 05/13/2021
targetos: Windows
description: The D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1 structure describes statistics for each stage of the graphics pipeline that is used in a call to the pfnBeginEndQuery function to create a D3D12_QUERY_TYPE_PIPELINE_STATISTICS1 query type, and in a call to pfnResolveQueryData to return information about the query.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
f1_keywords:
 - D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
 - d3d12umddi/D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1
dev_langs:
 - c++
---

## -description

The **D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1** structure describes statistics for each stage of the graphics pipeline that is used in a call to the [**pfnBeginEndQuery**](nc-d3d12umddi-pfnd3d12ddi_begin_end_query.md) function to create a **D3D12_QUERY_TYPE_PIPELINE_STATISTICS1** query type, and in a call to [**pfnResolveQueryData**](nc-d3d12umddi-pfnd3d12ddi_resolve_query_data.md) to return information about the query.

## -struct-fields

### -field IAVertices

The number of input assembler (IA) vertices.

### -field IAPrimitives

The number of IA primitives.

### -field VSInvocations

The number of vertex shader (VS) invocations.

### -field GSInvocations

The number of geometry shader (GS) invocations.

### -field GSPrimitives

The number of GS primitives.

### -field CInvocations

The number of clipper invocations.

### -field CPrimitives

The number of clipper primitives.

### -field PSInvocations

The number of pixel shader (PS) invocations.

### -field HSInvocations

The number of hull shader (HS) invocations.

### -field DSInvocations

The number of domain shader (DS) invocations.

### -field CSInvocations

The number of compute shader (CS) invocations.

### -field ASInvocations

The number of amplification shader (AS) invocations.

### -field MSInvocations

The number of mesh shader (MS) invocations.

### -field MSPrimitives

The number of primitives output by the MS.

## -remarks

The driver associates a **D3D12DDI_QUERY_DATA_PIPELINE_STATISTICS1** structure with the **D3D12DDI_QUERY_TYPE_PIPELINE_STATISTICS1** query type value for the [**D3D12DDI_QUERY_TYPE**](ne-d3d12umddi-d3d12ddi_query_type.md) and [**D3D12DDI_QUERY_HEAP_TYPE**](ne-d3d12umddi-d3d12ddi_query_heap_type.md) enumerations.

## -see-also

[**D3D12DDI_QUERY_HEAP_TYPE**](ne-d3d12umddi-d3d12ddi_query_heap_type.md)

[**D3D12DDI_QUERY_TYPE**](ne-d3d12umddi-d3d12ddi_query_type.md)

[**pfnBeginEndQuery**](nc-d3d12umddi-pfnd3d12ddi_begin_end_query.md)

[**pfnResolveQueryData**](nc-d3d12umddi-pfnd3d12ddi_resolve_query_data.md)
