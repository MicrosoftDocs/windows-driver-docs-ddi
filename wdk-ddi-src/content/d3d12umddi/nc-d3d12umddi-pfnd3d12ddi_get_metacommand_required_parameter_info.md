---
UID: NC:d3d12umddi.PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO
title: PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO
author: windows-driver-content
description:
ms.assetid: 65e07c66-e3ac-42b4-bdba-146204a3f097
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
-	PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO
product: 
- Windows
targetos: Windows
---

# PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO callback function

## -description

Implemented by the client driver to get required information for a meta-command.

## -prototype

```
//Declaration

PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO Pfnd3d12ddiGetMetacommandRequiredParameterInfo;

// Definition

VOID Pfnd3d12ddiGetMetacommandRequiredParameterInfo
(
	 D3D12DDI_HMETACOMMAND
	UINT32 ParameterIndex
	D3D12DDIARG_METACOMMAND_REQUIRED_PARAMETER_INFO *
)
{...}

PFND3D12DDI_GET_METACOMMAND_REQUIRED_PARAMETER_INFO


```

## -parameters

### -param D3D12DDI_HMETACOMMAND

A handle to a meta-command.

### -param ParameterIndex

The index of the parameter.

### -param D3D12DDIARG_METACOMMAND_REQUIRED_PARAMETER_INFO * [out]

A pointer to a D3D12DDIARG_METACOMMAND_REQUIRED_PARAMETER_INFO structure that contains the meta-command's required parameter info.

## -returns

This callback function does not return a value.

