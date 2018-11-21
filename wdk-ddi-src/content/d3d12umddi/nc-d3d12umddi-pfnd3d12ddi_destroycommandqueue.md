---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYCOMMANDQUEUE
title: PFND3D12DDI_DESTROYCOMMANDQUEUE
author: windows-driver-content
description: Destroys a command queue.
ms.assetid: 751d9b9d-9f0e-4ded-a15a-cae5efeea015
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_DESTROYCOMMANDQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROYCOMMANDQUEUE callback function

## -description

Destroys a command queue.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYCOMMANDQUEUE Pfnd3d12ddiDestroycommandqueue; 

// Definition

VOID Pfnd3d12ddiDestroycommandqueue 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDQUEUE
)
{...}

PFND3D12DDI_DESTROYCOMMANDQUEUE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HCOMMANDQUEUE: 

A command queue handle.

## -returns

Returns VOID.

## -remarks




## -see-also
