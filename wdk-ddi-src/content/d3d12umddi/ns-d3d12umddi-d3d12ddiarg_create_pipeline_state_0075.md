---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_PIPELINE_STATE_0075
title: D3D12DDIARG_CREATE_PIPELINE_STATE_0075
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
ms.assetid: 68a5bb92-22cf-4f87-aae6-8e5fc78c0e75
tech.root: display
description: Creates a pipeline state.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATE_PIPELINE_STATE_0075
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_PIPELINE_STATE_0075
f1_keywords:
 - D3D12DDIARG_CREATE_PIPELINE_STATE_0075
 - d3d12umddi/D3D12DDIARG_CREATE_PIPELINE_STATE_0075
dev_langs:
 - c++
---

## -description

Creates a pipeline state.

## -struct-fields

### -field hComputeShader

The compute shader.

### -field hVertexShader

The vertex shader.

### -field hPixelShader

The pixel shader.

### -field hDomainShader

The domain shader.

### -field hHullShader

The hull shader.

### -field hGeometryShader

The geometry shader.

### -field hRootSignature

The root signature.

### -field hBlendState

The blend state.

### -field SampleMask

The sample mask.

### -field hRasterizerState

The rasterizer state.

### -field hDepthStencilState

The depth stencil state.

### -field hElementLayout

The element layout.

### -field IBStripCutValue

The index buffer strip cut value.

### -field PrimitiveTopologyType

The primitive topology type.

### -field NumRenderTargets

The number of render targets.

### -field RTVFormats

The RTV formats.

### -field DSVFormat

The DSV format.

### -field SampleDesc

The sample description.

### -field NodeMask

Represents the set of nodes.

### -field LibraryReference

The library reference.

### -field ViewInstancingDesc

The view instancing description.

### -field hMeshShader

The mesh shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

### -field hAmplificationShader

The amplification shader. See the [Mesh Shader Specification](https://microsoft.github.io/DirectX-Specs/d3d/MeshShader.html) for more information.

## -remarks

## -see-also

