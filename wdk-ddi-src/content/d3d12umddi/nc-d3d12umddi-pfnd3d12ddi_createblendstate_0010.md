---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEBLENDSTATE_0010
title: PFND3D12DDI_CREATEBLENDSTATE_0010
author: windows-driver-content
description: 
ms.assetid: 84568c55-656d-4668-8b37-4e3dcae345d5
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
-	PFND3D12DDI_CREATEBLENDSTATE_0010
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATEBLENDSTATE_0010 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATEBLENDSTATE_0010 Pfnd3d12ddiCreateblendstate0010; 

// Definition

VOID Pfnd3d12ddiCreateblendstate0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_BLEND_DESC_0010 *
	 D3D12DDI_HBLENDSTATE
)
{...}

PFND3D12DDI_CREATEBLENDSTATE_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param D3D12DDI_HBLENDSTATE: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also