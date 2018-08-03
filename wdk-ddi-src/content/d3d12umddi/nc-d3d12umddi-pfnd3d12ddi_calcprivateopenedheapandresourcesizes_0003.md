---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003
title: PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003
author: windows-driver-content
description: 
ms.assetid: fadc2a19-60d0-4c03-8f03-62bd629186ac
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
-	PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0003; 

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
)
{...}

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also