---
UID: NC:d3d12umddi.PFND3D12DDI_GETMIPPACKING
title: PFND3D12DDI_GETMIPPACKING
author: windows-driver-content
description: Gets MIP packing info.
ms.assetid: 9b95e67c-7a52-4ae2-814a-b0358b0cb755
ms.date: 10/19/2018
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
-	PFND3D12DDI_GETMIPPACKING
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_GETMIPPACKING callback function

## -description

Gets MIP packing info.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GETMIPPACKING Pfnd3d12ddiGetmippacking; 

// Definition

VOID Pfnd3d12ddiGetmippacking 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HRESOURCE hTiledResource
	UINT *pNumPackedMips
	UINT *pNumTilesForPackedMips
)
{...}

PFND3D12DDI_GETMIPPACKING 


```

## -parameters

### -param hDevice

A device handle.

### -param hTiledResource

A tiled resource handle.

### -param *pNumPackedMips

Pointer to the number of packed MIPs.

### -param *pNumTilesForPackedMips

Pointer to the number of tiles for packed MIPs.

## -returns

Returns VOID.

## -remarks




## -see-also
