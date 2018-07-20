---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEFENCE
title: PFND3D12DDI_CREATEFENCE
author: windows-driver-content
description: 
ms.assetid: dcfe2112-bb20-4808-9cd3-59aa56875af7
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
-	PFND3D12DDI_CREATEFENCE
product: Windows
targetos: Windows
---

# PFND3D12DDI_CREATEFENCE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATEFENCE Pfnd3d12ddiCreatefence; 

// Definition

HRESULT Pfnd3d12ddiCreatefence 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HFENCE
	CONST D3D12DDIARG_CREATE_FENCE *
)
{...}

PFND3D12DDI_CREATEFENCE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HFENCE: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also