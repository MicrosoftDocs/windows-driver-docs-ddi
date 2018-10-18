---
UID: NC:d3dkmthk.PFND3DKMT_UNPINDIRECTFLIPRESOURCES
title: PFND3DKMT_UNPINDIRECTFLIPRESOURCES
author: windows-driver-content
description: The PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function unpins direct flip resources.
ms.assetid: 4b2692d3-7747-490e-9f90-45f8d4cfbf72
ms.date: 
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
-	PFND3DKMT_UNPINDIRECTFLIPRESOURCES
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function

## -description

The PFND3DKMT_UNPINDIRECTFLIPRESOURCES callback function unpins direct flip resources.

## -prototype

```cpp
//Declaration

PFND3DKMT_UNPINDIRECTFLIPRESOURCES Pfnd3dkmtUnpindirectflipresources; 

// Definition

NTSTATUS Pfnd3dkmtUnpindirectflipresources 
(
	const D3DKMT_UNPINDIRECTFLIPRESOURCES *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_UNPINDIRECTFLIPRESOURCES](ns-d3dkmthk-_d3dkmt_unpindirectflipresources.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
