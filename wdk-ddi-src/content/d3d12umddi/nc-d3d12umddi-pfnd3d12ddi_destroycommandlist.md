---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCOMMANDLIST
title: PFND3D12DDI_DESTROYCOMMANDLIST (d3d12umddi.h)
description: Destroys a command list.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROYCOMMANDLIST callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
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
 - PFND3D12DDI_DESTROYCOMMANDLIST
 - d3d12umddi/PFND3D12DDI_DESTROYCOMMANDLIST
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYCOMMANDLIST
dev_langs:
 - c++
---

# PFND3D12DDI_DESTROYCOMMANDLIST callback function


## -description

Destroys a command list.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

A command list handle.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYCOMMANDLIST Pfnd3d12ddiDestroycommandlist; 

// Definition

VOID Pfnd3d12ddiDestroycommandlist 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDLIST
)
{...}

PFND3D12DDI_DESTROYCOMMANDLIST 


```

## -remarks

## -see-also

