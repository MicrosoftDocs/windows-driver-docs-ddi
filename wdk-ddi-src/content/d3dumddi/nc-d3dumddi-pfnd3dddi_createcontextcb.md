---
UID: NC:d3dumddi.PFND3DDDI_CREATECONTEXTCB
title: PFND3DDDI_CREATECONTEXTCB
author: windows-driver-content
description: The PFND3DDDI_CREATECONTEXTCB callback function creates a context.
ms.assetid: ff14eb10-d4fe-427f-be95-558c2f86fc01
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dumddi.h
api_name: 
-	PFND3DDDI_CREATECONTEXTCB
product:
-	Windows
targetos: Windows
---

# PFND3DDDI_CREATECONTEXTCB callback function

## -description

The PFND3DDDI_CREATECONTEXTCB callback function creates a context.

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

## -parameters

### -param hDevice

A handle to the graphics context device.

### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
