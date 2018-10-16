---
UID: NC:d3d12umddi.PFND3D12DDI_OPENHEAPANDRESOURCE_0043
title: PFND3D12DDI_OPENHEAPANDRESOURCE_0043
author: windows-driver-content
description: Implemented by the client driver to open heap and resource.
ms.assetid: e4387638-208c-4ea7-9858-773c2da0d2ba
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_OPENHEAPANDRESOURCE_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_OPENHEAPANDRESOURCE_0043 callback function

## -description

Implemented by the client driver to open heap and resource.

## -prototype

```cpp
//Declaration

PFND3D12DDI_OPENHEAPANDRESOURCE_0043 Pfnd3d12ddiOpenheapandresource0043;

// Definition

HRESULT Pfnd3d12ddiOpenheapandresource0043
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	 D3D12DDI_HPROTECTEDRESOURCESESSION_0030
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_OPENHEAPANDRESOURCE_0043


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_OPENHEAP_0003 *

Open heap and resource.

### -param

Used to create a heap.

### -param D3D12DDI_HRTRESOURCE

Used to create a resource.

### -param D3D12DDI_HPROTECTEDRESOURCESESSION_0030

The protected resource session.

### -param D3D12DDI_HRESOURCE

The hardware resource.

## -returns

Returns STATUS_SUCCESS if completed successfully.


## -see-also
