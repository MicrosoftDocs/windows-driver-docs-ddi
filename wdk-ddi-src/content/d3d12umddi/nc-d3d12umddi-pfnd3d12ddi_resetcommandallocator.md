---
UID: NC:d3d12umddi.PFND3D12DDI_RESETCOMMANDALLOCATOR
title: PFND3D12DDI_RESETCOMMANDALLOCATOR
author: windows-driver-content
description: 
ms.assetid: f706c981-a156-4fa1-96c1-7bb823f6d2d9
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
-	PFND3D12DDI_RESETCOMMANDALLOCATOR
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_RESETCOMMANDALLOCATOR callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_RESETCOMMANDALLOCATOR Pfnd3d12ddiResetcommandallocator; 

// Definition

VOID Pfnd3d12ddiResetcommandallocator 
(
	 D3D12DDI_HCOMMANDALLOCATOR
)
{...}

PFND3D12DDI_RESETCOMMANDALLOCATOR 


```

## -parameters

### -param D3D12DDI_HCOMMANDALLOCATOR: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also