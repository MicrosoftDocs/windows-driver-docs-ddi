---
UID: NE:d3d10umddi.D3D11DDI_HANDLETYPE
title: D3D11DDI_HANDLETYPE
author: windows-driver-content
description: Contains values that identify handle types.
old-location: display\d3d11ddi_handletype.htm
old-project: display
ms.assetid: 9ac032fe-b870-49aa-8602-3c7aa997ef9a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/ D3D12DDI_HT_DESCRIPTOR_HEAP, D3D12DDI_HT_HEAP, D3D11DDI_HANDLETYPE, D3D11_1DDI_HT_VIDEOPROCESSORENUM, d3d10umddi/D3D10DDI_HT_SAMPLERSTATE, d3d10umddi/ D3D12DDI_HT_COMMAND_ALLOCATOR, D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER, d3d10umddi/ D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER, D3D10DDI_HT_BLENDSTATE, d3d10umddi/ D3D12DDI_HT_COMMAND_QUEUE, D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW, d3d10umddi/ D3D12DDI_HT_PIPELINE_STATE, d3d10umddi/ D3D12DDI_HT_FENCE, d3d10umddi/D3D10DDI_HT_SHADERRESOURCEVIEW, d3d10umddi/ D3D12DDI_HT_HEAP, d3d10umddi/D3D10DDI_HT_RENDERTARGETVIEW, D3D10DDI_HT_SHADER, D3D10DDI_HT_ELEMENTLAYOUT, D3D11_1DDI_HT_DECODE, D3D10DDI_HT_DEPTHSTENCILSTATE, D3D11DDI_HANDLETYPE enumeration [Display Devices], d3d10umddi/D3D11DDI_HANDLETYPE, d3d10umddi/D3D11_1DDI_HT_DECODE, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSORENUM, D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW, D3D12DDI_HT_DESCRIPTOR_HEAP, D3D12DDI_HT_FENCE, D3D10DDI_HT_RASTERIZERSTATE, D3D10DDI_HT_SAMPLERSTATE, d3d10umddi/D3D11DDI_HT_COMMANDLIST, D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW, D3D10DDI_HT_QUERY, d3d10umddi/D3D10DDI_HT_RASTERIZERSTATE, D3D11_1DDI_HT_VIDEOPROCESSOR, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSOR, D3D10DDI_HT_DEPTHSTENCILVIEW, d3d10umddi/D3D10DDI_HT_BLENDSTATE, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW, d3d10umddi/D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW, d3d10umddi/D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW, D3D12DDI_HT_COMMAND_QUEUE, d3d10umddi/D3D10DDI_HT_DEPTHSTENCILVIEW, d3d10umddi/D3D10DDI_HT_SHADER, D3D12DDI_HT_PIPELINE_STATE, D3D12DDI_HT_COMMAND_LIST, UMDisplayDriver_Dx11param_Structs_b979aef9-205a-4af9-b68e-9064499faca5.xml, d3d10umddi/ D3D12DDI_HT_COMMAND_LIST, D3D10DDI_HT_SHADERRESOURCEVIEW, d3d10umddi/D3D11DDI_HT_UNORDEREDACCESSVIEW, d3d10umddi/D3D10DDI_HT_RESOURCE, D3D10DDI_HT_RESOURCE, D3D10DDI_HT_RENDERTARGETVIEW, display.d3d11ddi_handletype, d3d10umddi/D3D10DDI_HT_DEPTHSTENCILSTATE, d3d10umddi/D3D10DDI_HT_ELEMENTLAYOUT, d3d10umddi/D3D10DDI_HT_QUERY, D3D11DDI_HT_COMMANDLIST, D3D11DDI_HT_UNORDEREDACCESSVIEW, D3D12DDI_HT_COMMAND_ALLOCATOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_HANDLETYPE is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname:
-	D3D11DDI_HANDLETYPE
product: Windows
targetos: Windows
req.typenames: D3D11DDI_HANDLETYPE
---

# D3D11DDI_HANDLETYPE enumeration


## -description


Contains values that identify handle types. 


## -syntax


````
typedef enum D3D11DDI_HANDLETYPE { 
  D3D10DDI_HT_RESOURCE                           = 0,
  D3D10DDI_HT_SHADERRESOURCEVIEW                 = 1,
  D3D10DDI_HT_RENDERTARGETVIEW                   = 2,
  D3D10DDI_HT_DEPTHSTENCILVIEW                   = 3,
  D3D10DDI_HT_SHADER                             = 4,
  D3D10DDI_HT_ELEMENTLAYOUT                      = 5,
  D3D10DDI_HT_BLENDSTATE                         = 6,
  D3D10DDI_HT_DEPTHSTENCILSTATE                  = 7,
  D3D10DDI_HT_RASTERIZERSTATE                    = 8,
  D3D10DDI_HT_SAMPLERSTATE                       = 9,
  D3D10DDI_HT_QUERY                              = 10,
  D3D11DDI_HT_COMMANDLIST                        = 11,
  D3D11DDI_HT_UNORDEREDACCESSVIEW                = 12,
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDI_HT_DECODE                           = 13,
  D3D11_1DDI_HT_VIDEOPROCESSORENUM               = 14,
  D3D11_1DDI_HT_VIDEOPROCESSOR                   = 15,
  D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW           = 16,
  D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW          = 17,
  D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW         = 18,
#endif 
#if D3D12DDI_MINOR_HEADER_VERSION >= 2
      D3D12DDI_HT_COMMAND_QUEUE                  = ,
      D3D12DDI_HT_COMMAND_ALLOCATOR              = ,
      D3D12DDI_HT_PIPELINE_STATE                 = ,
      D3D12DDI_HT_COMMAND_LIST                   = ,
      D3D12DDI_HT_FENCE                          = ,
      D3D12DDI_HT_DESCRIPTOR_HEAP                = ,
      D3D12DDI_HT_HEAP                           = ,
      D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER  = 

#endif } D3D11DDI_HANDLETYPE;
````


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




#### - D3D12DDI_HT_COMMAND_QUEUE

Supported starting with Windows 10.


#### - D3D12DDI_HT_COMMAND_ALLOCATOR

Supported starting with Windows 10.


#### - D3D12DDI_HT_PIPELINE_STATE

Supported starting with Windows 10.


#### - D3D12DDI_HT_COMMAND_LIST

Supported starting with Windows 10.


#### - D3D12DDI_HT_FENCE

Supported starting with Windows 10.


#### - D3D12DDI_HT_DESCRIPTOR_HEAP

Supported starting with Windows 10.


#### - D3D12DDI_HT_HEAP

Supported starting with Windows 10.


#### - D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER

Supported starting with Windows 10.

