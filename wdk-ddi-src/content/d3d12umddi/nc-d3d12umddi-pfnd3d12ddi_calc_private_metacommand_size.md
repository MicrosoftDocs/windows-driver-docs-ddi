---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE
title: PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE (d3d12umddi.h)
description: Calculates the private meta-command size.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE"
 - "PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE"
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
req.max-support: Windows 10, version 1803
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
- PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE callback function

## -description

Calculates the private meta-command size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE Pfnd3d12ddiCalcPrivateMetacommandSize;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateMetacommandSize
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_METACOMMAND_DESC *
)
{...}

PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_METACOMMAND_DESC

The meta-command description.

## -returns

Returns SIZE_T that describes the meta-command size.

