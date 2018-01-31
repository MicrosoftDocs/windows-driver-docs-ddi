---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_PIPELINE_STATE_0033
title: D3D12DDIARG_CREATE_PIPELINE_STATE_0033
author: windows-driver-content
description: Creates a pipeline state.
old-location: display\d3d12ddiarg-create-pipeline-state-0033.htm
old-project: display
ms.assetid: 2a9108ab-5852-4053-9a7a-266ae1b1dced
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDIARG_CREATE_PIPELINE_STATE_0033 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_PIPELINE_STATE_0033, display.d3d12ddiarg-create-pipeline-state-0033, D3D12DDIARG_CREATE_PIPELINE_STATE_0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDIARG_CREATE_PIPELINE_STATE_0033
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_PIPELINE_STATE_0033
---

# D3D12DDIARG_CREATE_PIPELINE_STATE_0033 structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Creates a pipeline state.


## -syntax


````
typedef struct _D3D12DDIARG_CREATE_PIPELINE_STATE_0033 {
  D3D12DDI_HSHADER                       hComputeShader;
  D3D12DDI_HSHADER                       hVertexShader;
  D3D12DDI_HSHADER                       hPixelShader;
  D3D12DDI_HSHADER                       hDomainShader;
  D3D12DDI_HSHADER                       hHullShader;
  D3D12DDI_HSHADER                       hGeometryShader;
  D3D12DDI_HROOTSIGNATURE                hRootSignature;
  D3D12DDI_HBLENDSTATE                   hBlendState;
  UINT                                   SampleMask;
  D3D12DDI_HRASTERIZERSTATE              hRasterizerState;
  D3D12DDI_HDEPTHSTENCILSTATE            hDepthStencilState;
  D3D12DDI_HELEMENTLAYOUT                hElementLayout;
  D3D12DDI_INDEX_BUFFER_STRIP_CUT_VALUE  IBStripCutValue;
  D3D12DDI_PRIMITIVE_TOPOLOGY_TYPE       PrimitiveTopologyType;
  UINT                                   NumRenderTargets;
  DXGI_FORMAT [8]                        RTVFormats;
  DXGI_FORMAT                            DSVFormat;
  DXGI_SAMPLE_DESC                       SampleDesc;
  UINT                                   NodeMask;
  D3D12DDI_LIBRARY_REFERENCE_0010        LibraryReference;
  D3D12DDI_VIEW_INSTANCING_DESC          ViewInstancingDesc;
} D3D12DDIARG_CREATE_PIPELINE_STATE_0033, D3D12DDIARG_CREATE_PIPELINE_STATE_0033;
````


## -struct-fields




#### - hComputeShader

The compute shader.


#### - hVertexShader

The vertex shader.


#### - hPixelShader

The pixel shader.


#### - hDomainShader

The domain shader.


#### - hHullShader

The hull shader.


#### - hGeometryShader

The geometry shader.


#### - hRootSignature

The root signature.


#### - hBlendState

The blend state.


#### - SampleMask

The sample mask.


#### - hRasterizerState

The rasterizer state.


#### - hDepthStencilState

The depth stencil state.


#### - hElementLayout

The element layout.


#### - IBStripCutValue

The index buffer strip cut value.


#### - PrimitiveTopologyType

The primitive topology type.


#### - NumRenderTargets

The number of render targets.


#### - RTVFormats

The RTV formats.


#### - DSVFormat

The DSV format.


#### - SampleDesc

The sample description.


#### - NodeMask

Represents the set of nodes.


#### - LibraryReference

The library reference.


#### - ViewInstancingDesc

The view instancing description.

