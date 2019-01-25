---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE (d3d12umddi.h)
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
tech.root: display
ms.assetid: 9bae8daf-8162-42cf-8087-6ace5f910cbd
ms.date: 11/28/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
 - PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE callback function

## -description

Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEBLENDSTATESIZE Pfnd3d12ddiCalcprivateblendstatesize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivateblendstatesize 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDI_BLEND_DESC *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

A pointer to a D3D12DDI_BLEND_DESC structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns SIZE_T.

## -remarks

## -see-also
