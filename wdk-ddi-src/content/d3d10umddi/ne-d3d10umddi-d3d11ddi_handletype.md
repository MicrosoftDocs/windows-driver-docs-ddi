---
UID: NE:d3d10umddi.D3D11DDI_HANDLETYPE
title: D3D11DDI_HANDLETYPE (d3d10umddi.h)
description: Contains values that identify handle types.
old-location: display\d3d11ddi_handletype.htm
ms.date: 08/22/2022
keywords: ["D3D11DDI_HANDLETYPE enumeration"]
ms.keywords: D3D10DDI_HT_BLENDSTATE, D3D10DDI_HT_DEPTHSTENCILSTATE, D3D10DDI_HT_DEPTHSTENCILVIEW, D3D10DDI_HT_ELEMENTLAYOUT, D3D10DDI_HT_QUERY, D3D10DDI_HT_RASTERIZERSTATE, D3D10DDI_HT_RENDERTARGETVIEW, D3D10DDI_HT_RESOURCE, D3D10DDI_HT_SAMPLERSTATE, D3D10DDI_HT_SHADER, D3D10DDI_HT_SHADERRESOURCEVIEW, D3D11DDI_HANDLETYPE, D3D11DDI_HANDLETYPE enumeration [Display Devices], D3D11DDI_HT_COMMANDLIST, D3D11DDI_HT_UNORDEREDACCESSVIEW, D3D11_1DDI_HT_DECODE, D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW, D3D11_1DDI_HT_VIDEOPROCESSOR, D3D11_1DDI_HT_VIDEOPROCESSORENUM, D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW, D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW, D3D12DDI_HT_COMMAND_ALLOCATOR, D3D12DDI_HT_COMMAND_LIST, D3D12DDI_HT_COMMAND_QUEUE, D3D12DDI_HT_DESCRIPTOR_HEAP, D3D12DDI_HT_FENCE, D3D12DDI_HT_HEAP, D3D12DDI_HT_PIPELINE_STATE, D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER, UMDisplayDriver_Dx11param_Structs_b979aef9-205a-4af9-b68e-9064499faca5.xml, d3d10umddi/ D3D12DDI_HT_COMMAND_ALLOCATOR, d3d10umddi/ D3D12DDI_HT_COMMAND_LIST, d3d10umddi/ D3D12DDI_HT_COMMAND_QUEUE, d3d10umddi/ D3D12DDI_HT_DESCRIPTOR_HEAP, d3d10umddi/ D3D12DDI_HT_FENCE, d3d10umddi/ D3D12DDI_HT_HEAP, d3d10umddi/ D3D12DDI_HT_PIPELINE_STATE, d3d10umddi/ D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER, d3d10umddi/D3D10DDI_HT_BLENDSTATE, d3d10umddi/D3D10DDI_HT_DEPTHSTENCILSTATE, d3d10umddi/D3D10DDI_HT_DEPTHSTENCILVIEW, d3d10umddi/D3D10DDI_HT_ELEMENTLAYOUT, d3d10umddi/D3D10DDI_HT_QUERY, d3d10umddi/D3D10DDI_HT_RASTERIZERSTATE, d3d10umddi/D3D10DDI_HT_RENDERTARGETVIEW, d3d10umddi/D3D10DDI_HT_RESOURCE, d3d10umddi/D3D10DDI_HT_SAMPLERSTATE, d3d10umddi/D3D10DDI_HT_SHADER, d3d10umddi/D3D10DDI_HT_SHADERRESOURCEVIEW, d3d10umddi/D3D11DDI_HANDLETYPE, d3d10umddi/D3D11DDI_HT_COMMANDLIST, d3d10umddi/D3D11DDI_HT_UNORDEREDACCESSVIEW, d3d10umddi/D3D11_1DDI_HT_DECODE, d3d10umddi/D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSOR, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSORENUM, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW, display.d3d11ddi_handletype
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
targetos: Windows
tech.root: display
req.typenames: D3D11DDI_HANDLETYPE
f1_keywords:
 - D3D11DDI_HANDLETYPE
 - d3d10umddi/D3D11DDI_HANDLETYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDI_HANDLETYPE
---

# D3D11DDI_HANDLETYPE enumeration

## -description

Contains values that identify handle types.

## -enum-fields

### -field D3D10DDI_HT_RESOURCE

A resource handle.

### -field D3D10DDI_HT_SHADERRESOURCEVIEW

A shader-resource-view handle.

### -field D3D10DDI_HT_RENDERTARGETVIEW

A render-target-view handle.

### -field D3D10DDI_HT_DEPTHSTENCILVIEW

A depth-stencil-view handle.

### -field D3D10DDI_HT_SHADER

A shader handle.

### -field D3D10DDI_HT_ELEMENTLAYOUT

A value that identifies an element-layout handle.

### -field D3D10DDI_HT_BLENDSTATE

A blend-state handle.

### -field D3D10DDI_HT_DEPTHSTENCILSTATE

A depth-stencil-state handle.

### -field D3D10DDI_HT_RASTERIZERSTATE

A rasterizer-state handle.

### -field D3D10DDI_HT_SAMPLERSTATE

A sampler-state handle.

### -field D3D10DDI_HT_QUERY

A query handle.

### -field D3D11DDI_HT_COMMANDLIST

A command-list handle.

### -field D3D11DDI_HT_UNORDEREDACCESSVIEW

An unordered-access-view handle.

### -field D3D11_1DDI_HT_DECODE

A video decoder handle.

Supported starting with Windows 8.

### -field D3D11_1DDI_HT_VIDEOPROCESSORENUM

A video processor enumeration handle.

Supported starting with Windows 8.

### -field D3D11_1DDI_HT_VIDEOPROCESSOR

A video processor handle.

Supported starting with Windows 8.

### -field D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW

A video decoder output-view handle.

Supported starting with Windows 8.

### -field D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW

A video processor input-view handle.

Supported starting with Windows 8.

### -field D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW

A video processor output-view handle.

Supported starting with Windows 8.

### -field D3DWDDM2_2DDI_HT_CACHESESSION

A cache session handle.

Supported starting with Windows 10 version 1703 (WDDM 2.2).
