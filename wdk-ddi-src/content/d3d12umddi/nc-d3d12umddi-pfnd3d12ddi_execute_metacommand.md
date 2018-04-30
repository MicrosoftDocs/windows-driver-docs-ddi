---
UID: NC:d3d12umddi.PFND3D12DDI_EXECUTE_METACOMMAND
title: PFND3D12DDI_EXECUTE_METACOMMAND
author: windows-driver-content
description:
ms.assetid: 0ba97840-c316-4905-b65b-f103da9d5fe4
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_EXECUTE_METACOMMAND
product: Windows
targetos: Windows
---

# PFND3D12DDI_EXECUTE_METACOMMAND callback function

## -description

Implemented by the client driver to execute the meta-command.

## -prototype

```
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