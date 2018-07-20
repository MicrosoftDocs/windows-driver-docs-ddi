---
UID: NC:d3d12umddi.PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
title: PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
author: windows-driver-content
description: 
ms.assetid: 3c06c20c-915f-41c7-949d-a41038317e07
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	d3d12umddi.h
apiname: 
-	PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003
product: Windows
targetos: Windows
---

# PFND3D12DDI_RETRIEVE_SHADER_COMMENT_0003 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HPIPELINESTATE: 
### -param *pBuffer: 
### -param *CharacterCountIncludingNullTerminator: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also