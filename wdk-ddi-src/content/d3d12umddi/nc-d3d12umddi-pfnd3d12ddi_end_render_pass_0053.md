---
UID: NC:d3d12umddi.PFND3D12DDI_END_RENDER_PASS_0053
title: PFND3D12DDI_END_RENDER_PASS_0053 (d3d12umddi.h)
description: The PFND3D12DDI_END_RENDER_PASS_0053 callback function ends a render pass. The function is called by a client driver.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_END_RENDER_PASS_0053 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_END_RENDER_PASS_0053
 - d3d12umddi/PFND3D12DDI_END_RENDER_PASS_0053
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_END_RENDER_PASS_0053
dev_langs:
 - c++
---

# PFND3D12DDI_END_RENDER_PASS_0053 callback function


## -description

Implemented by the client driver to end a Render Pass.

## -parameters

### -param unnamedParam1

A D3D12DDI_HCOMMANDLIST (command list) that contains the Render Pass.

## -prototype

```cpp
//Declaration

PFND3D12DDI_END_RENDER_PASS_0053 Pfnd3d12ddiEndRenderPass0053; 

// Definition

VOID Pfnd3d12ddiEndRenderPass0053 
(
	D3D12DDI_HCOMMANDLIST Arg1
)
{...}

```

## -remarks

## -see-also

