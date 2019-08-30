---
UID: NC:d3d12umddi.PFND3D12DDI_GET_SHADER_IDENTIFIER_0054
title: PFND3D12DDI_GET_SHADER_IDENTIFIER_0054 (d3d12umddi.h)
description: Retrieves the unique identifier for a shader that can be used in a shader record.
ms.assetid: 8b805532-df68-406b-871b-9022d3d1114c
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_GET_SHADER_IDENTIFIER_0054"
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
- PFND3D12DDI_GET_SHADER_IDENTIFIER_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3D12DDI_GET_SHADER_IDENTIFIER_0054 callback function

## -description

Retrieves the unique identifier for a shader that can be used in a shader record. 

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_SHADER_IDENTIFIER_0054 Pfnd3d12ddiGetShaderIdentifier0054; 

// Definition

void * Pfnd3d12ddiGetShaderIdentifier0054 
(
	D3D12DDI_HSTATEOBJECT_0054 Arg1
	LPCWSTR pExportName
)
{...}

```

## -parameters

### -param Arg1

A handle to a state object. The state object can be a collection or a ray tracing pipeline state object.

### -param pExportName

Entry point in the state object for which to retrieve an identifier.

## -returns

Returns a pointer to the shader identifier. If the shader isn’t fully resolved in the state object, the return value is nullptr.

## -remarks

The return data is valid as long as the state object it came from is valid. The size of the data returned is given by [GetShaderStackSize](nc-d3d12umddi-pfnd3d12ddi_get_shader_stack_size_0054.md) callback function. Applications should copy and cache this data to avoid the cost of searching for it in the state object if it will need to be retrieved many times. The place the identifier actually gets used is in shader records within shader tables in GPU memory, which it is up to the app to populate. 

The data itself globally identifies the shader, so even if the shader appears in a different state object (with same associations like any root signatures), it will have the same identifier.




## -see-also
