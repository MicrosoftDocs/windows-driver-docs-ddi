---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYDEPTHSTENCILSTATE
title: PFND3D12DDI_DESTROYDEPTHSTENCILSTATE (d3d12umddi.h)
description: Destroy depth stencil state.
ms.assetid: 36db022f-0740-4864-9f13-9bce157fdb3a
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_DESTROYDEPTHSTENCILSTATE
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_DESTROYDEPTHSTENCILSTATE callback function

## -description

Destroy depth stencil state.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYDEPTHSTENCILSTATE Pfnd3d12ddiDestroydepthstencilstate; 

// Definition

VOID Pfnd3d12ddiDestroydepthstencilstate 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HDEPTHSTENCILSTATE
)
{...}

PFND3D12DDI_DESTROYDEPTHSTENCILSTATE 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HDEPTHSTENCILSTATE: 

A depth stencil state handle.

## -returns

Returns VOID.

## -remarks




## -see-also
