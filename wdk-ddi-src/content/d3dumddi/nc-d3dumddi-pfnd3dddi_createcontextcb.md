---
UID: NC:d3dumddi.PFND3DDDI_CREATECONTEXTCB
title: PFND3DDDI_CREATECONTEXTCB (d3dumddi.h)
description: The PFND3DDDI_CREATECONTEXTCB callback function creates a context.
ms.date: 10/19/2018
keywords: ["PFND3DDDI_CREATECONTEXTCB callback function"]
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DDDI_CREATECONTEXTCB
 - d3dumddi/PFND3DDDI_CREATECONTEXTCB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_CREATECONTEXTCB
product:
 - Windows
dev_langs:
 - c++
---

# PFND3DDDI_CREATECONTEXTCB callback function


## -description

The PFND3DDDI_CREATECONTEXTCB callback function creates a context.

## -parameters

### -param hDevice

A handle to the graphics context device.

### -param Arg2

## -returns

Returns HRESULT that ...

## -prototype

```cpp
//Declaration

PFND3DDDI_CREATECONTEXTCB Pfnd3dddiCreatecontextcb; 

// Definition

HRESULT Pfnd3dddiCreatecontextcb 
(
	HANDLE hDevice
	D3DDDICB_CREATECONTEXT *
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.

## -see-also

