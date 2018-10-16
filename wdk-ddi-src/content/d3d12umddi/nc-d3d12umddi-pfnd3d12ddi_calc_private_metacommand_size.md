---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE
title: PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE
author: windows-driver-content
description: Calculates the private meta-command size.
ms.assetid: e1f4ad6e-a3a3-4145-9742-4b155b4d979c
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CALC_PRIVATE_METACOMMAND_SIZE
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

