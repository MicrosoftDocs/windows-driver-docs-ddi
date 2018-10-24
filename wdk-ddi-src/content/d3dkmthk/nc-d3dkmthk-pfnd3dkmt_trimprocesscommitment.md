---
UID: NC:d3dkmthk.PFND3DKMT_TRIMPROCESSCOMMITMENT
title: PFND3DKMT_TRIMPROCESSCOMMITMENT
author: windows-driver-content
description: Trim process commitment.
ms.assetid: f80d916f-aec5-4074-b934-51ec5eced878
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
-	PFND3DKMT_TRIMPROCESSCOMMITMENT
product:
-	Windows
targetos: Windows
---

# PFND3DKMT_TRIMPROCESSCOMMITMENT callback function

## -description

Trim process commitment.

## -prototype

```cpp
//Declaration

PFND3DKMT_TRIMPROCESSCOMMITMENT Pfnd3dkmtTrimprocesscommitment; 

// Definition

NTSTATUS Pfnd3dkmtTrimprocesscommitment 
(
	D3DKMT_TRIMPROCESSCOMMITMENT *
)
{...}

```

## -parameters

### -param * 

Pointer to a [D3DKMT_TRIMPROCESSCOMMITMENT](ns-d3dkmthk-_d3dkmt_trimprocesscommitment.md) structure.

## -returns

Returns NTSTATUS.


## -remarks




## -see-also
