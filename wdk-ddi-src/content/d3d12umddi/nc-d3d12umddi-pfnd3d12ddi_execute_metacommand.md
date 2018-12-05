---
UID: NC:d3d12umddi.PFND3D12DDI_EXECUTE_METACOMMAND
title: PFND3D12DDI_EXECUTE_METACOMMAND
author: windows-driver-content
description: Implemented by the client driver to execute the meta-command.
ms.assetid: 0ba97840-c316-4905-b65b-f103da9d5fe4
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
req.max-support: Windows 10, version 1803
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
-	PFND3D12DDI_EXECUTE_METACOMMAND
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_EXECUTE_METACOMMAND callback function

## -description

Implemented by the client driver to execute the meta-command.

## -prototype

```cpp
//Declaration

PFND3D12DDI_EXECUTE_METACOMMAND Pfnd3d12ddiExecuteMetacommand;

// Definition

VOID Pfnd3d12ddiExecuteMetacommand
(
	 D3D12DDI_HCOMMANDLIST
	 D3D12DDI_HMETACOMMAND
	CONST D3D12DDIARG_METACOMMAND_PARAMETER_DATA *
	UINT NumParameters
)
{...}

PFND3D12DDI_EXECUTE_METACOMMAND


```

## -parameters

### -param D3D12DDI_HCOMMANDLIST

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param D3D12DDI_HMETACOMMAND

A handle to the meta-command.

### -param D3D12DDIARG_METACOMMAND_PARAMETER_DATA *

A pointer to a D3D12DDIARG_METACOMMAND_PARAMETER_DATA structure.

### -param NumParameters

The number of parameters.

## -returns

This callback function does not return a value.



## -see-also
