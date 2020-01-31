---
UID: NC:d3d12umddi.PFND3D12DDI_BLT
title: PFND3D12DDI_BLT (d3d12umddi.h)
description: The Blt function copies the contents of a source surface to a destination surface.
tech.root: display
ms.assetid: 170ad11a-c97a-4f30-9d0d-73e3a5e3a9ad
ms.date: 11/28/2018
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
targetos: Windows
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_BLT"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_BLT
product:
 - Windows
---

# PFND3D12DDI_BLT callback function

## -description

The Blt function copies the contents of a source surface to a destination surface.

## -parameters

### -param Arg1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

A pointer to a D3D12DDIARG_BLT structure that describes the parameters of the bit-block transfer (bitblt).

## -prototype

```
//Declaration

PFND3D12DDI_BLT Pfnd3d12ddiBlt; 

// Definition

VOID Pfnd3d12ddiBlt 
(
	D3D12DDI_HCOMMANDLIST Arg1
	 const D3D12DDIARG_BLT *
)
{...}

```

## -remarks

## -see-also

