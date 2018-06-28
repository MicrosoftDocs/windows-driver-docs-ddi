---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDALLOCATOR
title: PFND3D12DDI_CREATECOMMANDALLOCATOR
author: windows-driver-content
description: 
ms.assetid: 78393c5e-a99a-4b55-8302-76137bc4f4e5
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
-	PFND3D12DDI_CREATECOMMANDALLOCATOR
product: Windows
targetos: Windows
---

# PFND3D12DDI_CREATECOMMANDALLOCATOR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATECOMMANDALLOCATOR Pfnd3d12ddiCreatecommandallocator; 

// Definition

HRESULT Pfnd3d12ddiCreatecommandallocator 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDALLOCATOR *
)
{...}

PFND3D12DDI_CREATECOMMANDALLOCATOR 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also