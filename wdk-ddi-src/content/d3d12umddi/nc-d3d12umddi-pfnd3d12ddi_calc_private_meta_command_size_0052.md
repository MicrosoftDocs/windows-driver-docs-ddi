---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
title: PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
author: windows-driver-content
description:  Calculates the private meta-command size.
ms.assetid: 072a7577-00ed-4c07-b0b3-112cad845491
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function

## -description

Calculates the private meta-command size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 Pfnd3d12ddiCalcPrivateMetaCommandSize0052; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateMetaCommandSize0052 
(
	D3D12DDI_HDEVICE Arg1
	GUID CommandId
	UINT NodeMask
	CONST void *pCreationParameters
	SIZE_T CreationParametersDataSizeInBytes
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param CommandId

The command id.

### -param NodeMask

The node mask of the command list.

### -param *pCreationParameters

The creation parameters.

### -param CreationParametersDataSizeInBytes: 

The size of the creation parameters.

## -returns

Returns SIZE_T.

## -remarks



## -see-also
