---
UID: NC:d3d12umddi.PFND3D12DDI_QUERY_NODE_MAP
title: PFND3D12DDI_QUERY_NODE_MAP
author: windows-driver-content
description: 
ms.assetid: e3b3025e-80a9-4dad-96fc-3298260a1742
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
-	PFND3D12DDI_QUERY_NODE_MAP
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_QUERY_NODE_MAP callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param NumPhysicalAdapters: 
### -param *pMap: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also