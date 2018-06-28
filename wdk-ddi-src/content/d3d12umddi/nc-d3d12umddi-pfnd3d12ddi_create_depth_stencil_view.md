---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
title: PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
author: windows-driver-content
description: 
ms.assetid: 0d574081-4505-4692-a774-9a490e0309fd
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
-	PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW
product: Windows
targetos: Windows
---

# PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW Pfnd3d12ddiCreateDepthStencilView; 

// Definition

VOID Pfnd3d12ddiCreateDepthStencilView 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_DEPTH_STENCIL_VIEW 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param DestDescriptor: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also