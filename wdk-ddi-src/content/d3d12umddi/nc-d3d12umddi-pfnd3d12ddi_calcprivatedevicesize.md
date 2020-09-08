---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEDEVICESIZE
title: PFND3D12DDI_CALCPRIVATEDEVICESIZE (d3d12umddi.h)
description: The CalcPrivateDeviceSize function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.
tech.root: display
ms.assetid: 989c35d8-c2bc-4738-ab14-85aeeb2bb3c3
ms.date: 11/28/2018
keywords: ["PFND3D12DDI_CALCPRIVATEDEVICESIZE callback function"]
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header: d3d12umddi.h
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
targetos: Windows
f1_keywords:
 - PFND3D12DDI_CALCPRIVATEDEVICESIZE
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEDEVICESIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEDEVICESIZE
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEDEVICESIZE callback function


## -description

The CalcPrivateDeviceSize function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.

## -parameters

### -param Arg1

A handle that identifies the graphics adapter.

### -param Arg2

A pointer to a D3D12DDIARG_CALCPRIVATEDEVICESIZE structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

Returns the size of the memory region that the driver requires to store frequently-accessed data.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEDEVICESIZE Pfnd3d12ddiCalcprivatedevicesize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatedevicesize 
(
	D3D12DDI_HADAPTER Arg1
	 const D3D12DDIARG_CALCPRIVATEDEVICESIZE *
)
{...}

```

## -remarks

## -see-also

