---
UID: NC:d3dkmthk.PFND3DKMT_FREEGPUVIRTUALADDRESS
title: PFND3DKMT_FREEGPUVIRTUALADDRESS (d3dkmthk.h)
description: The Pfnd3dkmtFreegpuvirtualaddress callback function releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_FREEGPUVIRTUALADDRESS callback function"]
req.header: d3dkmthk.h
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
 - PFND3DKMT_FREEGPUVIRTUALADDRESS
 - d3dkmthk/PFND3DKMT_FREEGPUVIRTUALADDRESS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_FREEGPUVIRTUALADDRESS
dev_langs:
 - c++
---

# PFND3DKMT_FREEGPUVIRTUALADDRESS callback function


## -description

The Pfnd3dkmtFreegpuvirtualaddress callback function releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_FREEGPUVIRTUALADDRESS](ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_FREEGPUVIRTUALADDRESS Pfnd3dkmtFreegpuvirtualaddress; 

// Definition

NTSTATUS Pfnd3dkmtFreegpuvirtualaddress 
(
	const D3DKMT_FREEGPUVIRTUALADDRESS *
)
{...}

```

## -remarks

## -see-also

