---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYFENCE
title: PFND3D12DDI_DESTROYFENCE
author: windows-driver-content
description: Destroy fence.
ms.assetid: 80fb2a47-384b-413a-a68f-1faedb114a17
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
-	PFND3D12DDI_DESTROYFENCE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYFENCE callback function

## -description

Destroy fence.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYFENCE Pfnd3d12ddiDestroyfence; 

// Definition

VOID Pfnd3d12ddiDestroyfence 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HFENCE
)
{...}

PFND3D12DDI_DESTROYFENCE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HFENCE: 

Fence handle.

## -returns

Returns VOID.

## -remarks




## -see-also
