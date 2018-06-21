---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE
title: PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE
author: windows-driver-content
description: 
ms.assetid: 40bbfdfa-e310-4e77-9e8c-2800a64f6bcb
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
-	PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE
product: Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE Pfnd3d12ddiCalcPrivateTessellationShaderSize; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateTessellationShaderSize 
(
	 D3D12DDI_HDEVICE
	CONST UINT *pShaderCode
	 D3D12DDI_HROOTSIGNATURE
	CONST D3D12DDIARG_TESSELLATION_IO_SIGNATURES *
)
{...}

PFND3D12DDI_CALC_PRIVATE_TESSELLATION_SHADER_SIZE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *pShaderCode: 
### -param D3D12DDI_HROOTSIGNATURE: 
### -param *: 



## -returns

Returns SIZE_T that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also