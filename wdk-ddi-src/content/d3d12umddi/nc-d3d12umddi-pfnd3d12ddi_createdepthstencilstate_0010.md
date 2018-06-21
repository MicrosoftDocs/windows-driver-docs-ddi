---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010
title: PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010
author: windows-driver-content
description: 
ms.assetid: f4a5fec5-216b-4488-987b-87cfeb3b3e2b
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
-	PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010
product: Windows
targetos: Windows
---

# PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010 Pfnd3d12ddiCreatedepthstencilstate0010; 

// Definition

VOID Pfnd3d12ddiCreatedepthstencilstate0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDI_DEPTH_STENCIL_DESC_0010 *
	 D3D12DDI_HDEPTHSTENCILSTATE
)
{...}

PFND3D12DDI_CREATEDEPTHSTENCILSTATE_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param D3D12DDI_HDEPTHSTENCILSTATE: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also