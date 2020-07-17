---
UID: NC:d3d12umddi.PFND3D12DDI_QUERY_NODE_MAP
title: PFND3D12DDI_QUERY_NODE_MAP (d3d12umddi.h)
description: Query node map.
ms.assetid: e3b3025e-80a9-4dad-96fc-3298260a1742
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_QUERY_NODE_MAP callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_QUERY_NODE_MAP"
 - "PFND3D12DDI_QUERY_NODE_MAP"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_QUERY_NODE_MAP
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_QUERY_NODE_MAP callback function

## -description

Query node map.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param NumPhysicalAdapters

The number of physical adapters.

### -param pMap

Pointer to a map.

## -prototype

```cpp
//Declaration

PFND3D12DDI_QUERY_NODE_MAP Pfnd3d12ddiQueryNodeMap; 

// Definition

VOID Pfnd3d12ddiQueryNodeMap 
(
	 D3D12DDI_HDEVICE
	UINT NumPhysicalAdapters
	UINT *pMap
)
{...}

PFND3D12DDI_QUERY_NODE_MAP 


```

## -remarks

## -see-also

