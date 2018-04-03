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
product: Windows
targetos: Windows
---

# PFND3DDDI_QUERYADAPTERINFOCB2 callback function

## -description

Implemented by the client driver to ... 

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

### -param hAdapter: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also