---
UID: NC:d3d12umddi.PFND3D12DDI_END_RENDER_PASS
title: PFND3D12DDI_END_RENDER_PASS (d3d12umddi.h)
description: Implemented by the client driver to end a Render Pass.
ms.assetid: ed21b9b2-3100-4d66-be48-f25567677427
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_END_RENDER_PASS"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_END_RENDER_PASS
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_END_RENDER_PASS callback function

## -description

Implemented by the client driver to end a Render Pass. 

## -prototype

```cpp
//Declaration

PFND3D12DDI_END_RENDER_PASS Pfnd3d12ddiEndRenderPass; 

// Definition

VOID Pfnd3d12ddiEndRenderPass 
(
	D3D12DDI_HCOMMANDLIST Arg1
)
{...}

```

## -parameters

### -param Arg1

A D3D12DDI_HCOMMANDLIST (command list) that contains the Render Pass.

## -returns

Returns VOID.

## -remarks




## -see-also
