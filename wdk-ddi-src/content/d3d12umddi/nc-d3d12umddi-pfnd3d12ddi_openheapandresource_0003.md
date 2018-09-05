---
UID: NC:d3d12umddi.PFND3D12DDI_OPENHEAPANDRESOURCE_0003
title: PFND3D12DDI_OPENHEAPANDRESOURCE_0003
author: windows-driver-content
description: 
ms.assetid: aca4ecce-657a-4288-b761-2c6463d039d8
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
-	PFND3D12DDI_OPENHEAPANDRESOURCE_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_OPENHEAPANDRESOURCE_0003 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 Pfnd3d12ddiOpenheapandresource0003; 

// Definition

HRESULT Pfnd3d12ddiOpenheapandresource0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param D3D12DDI_HHEAP: 
### -param D3D12DDI_HRTRESOURCE: 
### -param D3D12DDI_HRESOURCE: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also