---
UID: NC:d3d12umddi.PFND3D12DDI_EVICT2
title: PFND3D12DDI_EVICT2
author: windows-driver-content
description: 
ms.assetid: 2ebce9ab-3827-4fa4-848f-58c9eb10f82a
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
-	PFND3D12DDI_EVICT2
product: Windows
targetos: Windows
---

# PFND3D12DDI_EVICT2 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_EVICT2 Pfnd3d12ddiEvict2; 

// Definition

HRESULT Pfnd3d12ddiEvict2 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_EVICT *
)
{...}

PFND3D12DDI_EVICT2 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also