---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYBLENDSTATE
title: PFND3D12DDI_DESTROYBLENDSTATE
author: windows-driver-content
description: Destroys a blend state.
ms.assetid: eb4b3ebd-be63-41cf-af25-9c58ffe69deb
ms.date: 
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
-	PFND3D12DDI_DESTROYBLENDSTATE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYBLENDSTATE callback function

## -description

Destroys a blend state.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYBLENDSTATE Pfnd3d12ddiDestroyblendstate; 

// Definition

VOID Pfnd3d12ddiDestroyblendstate 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HBLENDSTATE
)
{...}

PFND3D12DDI_DESTROYBLENDSTATE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HBLENDSTATE: 

A blend state handle.

## -returns

Returns VOID.

## -remarks




## -see-also
