---
UID: NC:d3dumddi.PFND3DDDI_QUERYADAPTERINFOCB2
title: PFND3DDDI_QUERYADAPTERINFOCB2
author: windows-driver-content
description:
ms.assetid: f60b6167-b294-4f6e-9338-4f937a838712
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dumddi.h
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
-	d3dumddi.h
apiname:
-	PFND3DDDI_QUERYADAPTERINFOCB2
product: 
- Windows
targetos: Windows
---

# PFND3DDDI_QUERYADAPTERINFOCB2 callback function

## -description

Implemented by the client driver to retrieve graphics adapter information.

## -prototype

```
//Declaration

PFND3DDDI_QUERYADAPTERINFOCB2 Pfnd3dddiQueryadapterinfocb2;

// Definition

HRESULT Pfnd3dddiQueryadapterinfocb2
(
	HANDLE hAdapter
	CONST D3DDDICB_QUERYADAPTERINFO2 *
)
{...}

PFND3DDDI_QUERYADAPTERINFOCB2


```

## -parameters

### -param hAdapter

A handle to the graphics adapter object.

### -param D3DDDICB_QUERYADAPTERINFO2 *

A pointer to a [D3DDDICB_QUERYADAPTERINFO2](ns-d3dumddi-_d3dddicb_queryadapterinfo2.md) structure that receives information about the graphics hardware.

## -returns

<b>pfnQueryAdapterInfoCb2</b> returns one of the following values:

|Return code|Description|
|--|--|
|S_OK|Information was successfully retrieved.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|


This function might also return other HRESULT values.
