---
UID: NC:d3dkmthk.PFND3DKMT_FREEGPUVIRTUALADDRESS
title: PFND3DKMT_FREEGPUVIRTUALADDRESS
author: windows-driver-content
description: The Pfnd3dkmtFreegpuvirtualaddress callback function releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.
ms.assetid: c9072c10-4a54-4fa1-8bd5-c67cd876ccc6
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmthk.h
api_name: 
-	PFND3DKMT_FREEGPUVIRTUALADDRESS
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3DKMT_FREEGPUVIRTUALADDRESS callback function

## -description

The Pfnd3dkmtFreegpuvirtualaddress callback function releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.

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

## -parameters

### -param * 

Pointer to a [D3DKMT_FREEGPUVIRTUALADDRESS](ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
