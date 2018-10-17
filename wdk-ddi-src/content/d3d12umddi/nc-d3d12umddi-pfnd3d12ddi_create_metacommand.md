---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_METACOMMAND
title: PFND3D12DDI_CREATE_METACOMMAND
author: windows-driver-content
description: Implemented by the client driver to create meta-commands.
ms.assetid: a01b1dd8-2663-4ab6-82b7-01ae1b3d6661
ms.date:
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
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATE_METACOMMAND
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_METACOMMAND callback function

## -description

Implemented by the client driver to create meta-commands.

## -prototype

```
//Declaration

PFND3D12DDI_CREATE_METACOMMAND Pfnd3d12ddiCreateMetacommand;

// Definition

HRESULT Pfnd3d12ddiCreateMetacommand
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_METACOMMAND_DESC *
	 D3D12DDI_HMETACOMMAND
	 D3D12DDI_HRTMETACOMMAND
)
{...}

PFND3D12DDI_CREATE_METACOMMAND


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_METACOMMAND_DESC *

Pointer to a structure that contains meta-command fields.

### -param D3D12DDI_HMETACOMMAND

Handle to a meta command.

### -param D3D12DDI_HRTMETACOMMAND

A meta command.

## -returns

Returns an HRESULT.

## -remarks




## -see-also
