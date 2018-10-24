---
UID: NC:d3d12umddi.PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
title: PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
author: windows-driver-content
description: Implemented by the client driver to retrieve shader comment.
ms.assetid: 3c06c20c-915f-41c7-949d-a41038317e07
ms.date: 10/19/2018
ms.topic: callback
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
-	PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003 callback function

## -description

Implemented by the client driver to retrieve shader comment.

## -prototype

```cpp
//Declaration

PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003 Pfnd3d12ddiRetrieveShaderComment0003; 

// Definition

HRESULT Pfnd3d12ddiRetrieveShaderComment0003 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HPIPELINESTATE
	WCHAR *pBuffer
	SIZE_T *CharacterCountIncludingNullTerminator
)
{...}

PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HPIPELINESTATE

A handle to a pipeline state.

### -param *pBuffer

Pointer to a buffer.

### -param *CharacterCountIncludingNullTerminator

The character count, including the null terminator.

## -returns

Returns HRESULT.

## -remarks




## -see-also
