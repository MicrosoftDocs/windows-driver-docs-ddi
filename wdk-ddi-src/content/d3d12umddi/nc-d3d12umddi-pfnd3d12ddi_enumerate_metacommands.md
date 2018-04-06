---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_METACOMMANDS
title: PFND3D12DDI_ENUMERATE_METACOMMANDS
author: windows-driver-content
description:
ms.assetid: df59aa62-ee03-4ec3-bcab-8a50ef26a03b
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
-	PFND3D12DDI_ENUMERATE_METACOMMANDS
product: Windows
targetos: Windows
---

# PFND3D12DDI_ENUMERATE_METACOMMANDS callback function

## -description

Implemented by the client driver to enumerate meta-commands.

## -prototype

```
//Declaration

PFND3D12DDI_ENUMERATE_METACOMMANDS Pfnd3d12ddiEnumerateMetacommands;

// Definition

HRESULT Pfnd3d12ddiEnumerateMetacommands
(
	 D3D12DDI_HDEVICE
	UINT *pNumMetaCommands
	D3D12DDIARG_METACOMMAND_DESCRIPTION *pDescs
)
{...}

PFND3D12DDI_ENUMERATE_METACOMMANDS


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param *pNumMetaCommands

The number of meta-commands.

### -param *pDescs:

Pointer to an array of meta-command descriptions.

## -returns

Returns STATUS_SUCCESS if completed successfully.

