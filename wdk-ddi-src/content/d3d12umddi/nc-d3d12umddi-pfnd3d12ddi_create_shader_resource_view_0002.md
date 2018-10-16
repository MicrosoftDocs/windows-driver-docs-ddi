---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002
title: PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002
author: windows-driver-content
description: Create shader resource view.
ms.assetid: 90c30af4-5cf6-4a7e-b052-2f78a890b715
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002 callback function

## -description

Create shader resource view.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002 Pfnd3d12ddiCreateShaderResourceView0002; 

// Definition

VOID Pfnd3d12ddiCreateShaderResourceView0002 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_SHADER_RESOURCE_VIEW_0002 *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_SHADER_RESOURCE_VIEW_0002 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATE_SHADER_RESOURCE_VIEW_0002 structure.

### -param DestDescriptor: 

A CPU descriptor handle.

## -returns

Returns VOID.
