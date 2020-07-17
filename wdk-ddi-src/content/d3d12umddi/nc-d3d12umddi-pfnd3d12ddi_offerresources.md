---
UID: NC:d3d12umddi.PFND3D12DDI_OFFERRESOURCES
title: PFND3D12DDI_OFFERRESOURCES (d3d12umddi.h)
description: Offer resources.
ms.assetid: 794a29be-a6e8-4548-9de8-8230cb781cf8
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_OFFERRESOURCES callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_OFFERRESOURCES"
 - "PFND3D12DDI_OFFERRESOURCES"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_OFFERRESOURCES
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_OFFERRESOURCES callback function

## -description

Implemented by the client driver to offer resources.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a D3D12DDIARG_OFFERRESOURCES structure.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_OFFERRESOURCES Pfnd3d12ddiOfferresources; 

// Definition

HRESULT Pfnd3d12ddiOfferresources 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OFFERRESOURCES *
)
{...}

PFND3D12DDI_OFFERRESOURCES 


```

## -remarks

## -see-also

