---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKSUBRESOURCEINFO
title: PFND3D12DDI_CHECKSUBRESOURCEINFO (d3d12umddi.h)
description: Check subresource info.
ms.assetid: d8285aa5-1eec-425b-9cc5-28fa2e14b521
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CHECKSUBRESOURCEINFO callback function"]
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
 - "d3d12umddi/PFND3D12DDI_CHECKSUBRESOURCEINFO"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKSUBRESOURCEINFO
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKSUBRESOURCEINFO callback function

## -description

Check subresource info.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A resource handle.

### -param Subresource

The subresource index.

### -param Arg4

Pointer to a D3D12DDI_SUBRESOURCE_INFO.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKSUBRESOURCEINFO Pfnd3d12ddiChecksubresourceinfo; 

// Definition

VOID Pfnd3d12ddiChecksubresourceinfo 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
	UINT Subresource
	D3D12DDI_SUBRESOURCE_INFO *
)
{...}

PFND3D12DDI_CHECKSUBRESOURCEINFO 


```

