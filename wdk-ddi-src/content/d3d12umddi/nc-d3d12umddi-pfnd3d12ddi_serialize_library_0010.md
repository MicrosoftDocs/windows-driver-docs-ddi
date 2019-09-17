---
UID: NC:d3d12umddi.PFND3D12DDI_SERIALIZE_LIBRARY_0010
title: PFND3D12DDI_SERIALIZE_LIBRARY_0010 (d3d12umddi.h)
description: Implemented by the client driver to serialize the library.
ms.assetid: 7e23cd4e-e023-4b84-8335-587ff68242eb
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_SERIALIZE_LIBRARY_0010"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_SERIALIZE_LIBRARY_0010
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_SERIALIZE_LIBRARY_0010 callback function

## -description

Implemented by the client driver to serialize the library.

## -parameters

### -param hDevice

A device handle.

### -param hLibrary

A library handle.

### -param pBlob

Pointer to a blob.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_SERIALIZE_LIBRARY_0010 Pfnd3d12ddiSerializeLibrary0010; 

// Definition

HRESULT Pfnd3d12ddiSerializeLibrary0010 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HPIPELINELIBRARY hLibrary
	VOID *pBlob
)
{...}

PFND3D12DDI_SERIALIZE_LIBRARY_0010 


```

## -remarks

## -see-also

