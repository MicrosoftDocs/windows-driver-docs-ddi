---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_ROOT_SIGNATURE
title: PFND3D12DDI_DESTROY_ROOT_SIGNATURE (d3d12umddi.h)
description: Destroys a root signature.
ms.assetid: 3d30b10e-1cfe-4fbf-ba6b-b1bd3173e9f1
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
-	PFND3D12DDI_DESTROY_ROOT_SIGNATURE
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROY_ROOT_SIGNATURE callback function

## -description

Destroys a root signature.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_ROOT_SIGNATURE Pfnd3d12ddiDestroyRootSignature; 

// Definition

VOID Pfnd3d12ddiDestroyRootSignature 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HROOTSIGNATURE
)
{...}

PFND3D12DDI_DESTROY_ROOT_SIGNATURE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HROOTSIGNATURE: 

A root signature handle.

## -returns

Returns VOID.

## -remarks




## -see-also
