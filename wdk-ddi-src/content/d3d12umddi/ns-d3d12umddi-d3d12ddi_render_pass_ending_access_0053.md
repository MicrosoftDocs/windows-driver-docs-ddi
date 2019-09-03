---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053 (d3d12umddi.h)
description: Specifies the resources needed to end access to a Render Pass.
ms.assetid: f6732ebf-4a19-4054-8100-ec3f3ed0b7c6
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053"
ms.keywords: D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053, D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053 structure

## -description

Specifies the resources needed to end access to a Render Pass.

## -struct-fields

### -field Type
 
The [D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md). This allows the application to directly resolve a MSAA (Multisampling anti-aliasing) surface to a separate resource at the conclusion of the Render Pass.

### -field Resolve

The [D3D12DDI_RENDER_PASS_ENDING_ACCESS_RESOLVE_PARAMETERS_0053](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_resolve_parameters_0053.md).

## -remarks

## -see-also
