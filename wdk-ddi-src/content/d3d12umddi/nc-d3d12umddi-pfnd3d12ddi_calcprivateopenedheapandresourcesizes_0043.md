---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043
title: PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043
author: windows-driver-content
description:
ms.assetid: af4c6fb0-a10f-4abe-8161-2df2563b76cd
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
-	PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 callback function

## -description

Pointer to a CalcPrivateOpenedHeapAndResourceSizes function that calculates sizes for private opened heap and resources.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043 Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0043;

// Definition

D3D12DDI_HEAP_AND_RESOURCE_SIZES Pfnd3d12ddiCalcprivateopenedheapandresourcesizes0043
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HPROTECTEDRESOURCESESSION_0030
)
{...}

PFND3D12DDI_CALCPRIVATEOPENEDHEAPANDRESOURCESIZES_0043


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_OPENHEAP_0003

Open heap and resource.

### -param D3D12DDI_HPROTECTEDRESOURCESESSION_0030

The protected resource session.

## -returns

Returns D3D12DDI_HEAP_AND_RESOURCE_SIZES that contains the sizes for private opened heap and resources.

## -remarks



## -see-also