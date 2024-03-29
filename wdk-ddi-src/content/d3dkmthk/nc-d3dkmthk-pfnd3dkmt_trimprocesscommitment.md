---
UID: NC:d3dkmthk.PFND3DKMT_TRIMPROCESSCOMMITMENT
title: PFND3DKMT_TRIMPROCESSCOMMITMENT (d3dkmthk.h)
description: The PFND3DKMT_TRIMPROCESSCOMMITMENT callback function is invoked to trim a process commitment using information in the D3DKMT_TRIMPROCESSCOMMITMENT structure.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_TRIMPROCESSCOMMITMENT callback function"]
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
 - PFND3DKMT_TRIMPROCESSCOMMITMENT
 - d3dkmthk/PFND3DKMT_TRIMPROCESSCOMMITMENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_TRIMPROCESSCOMMITMENT
dev_langs:
 - c++
---

# PFND3DKMT_TRIMPROCESSCOMMITMENT callback function


## -description

Trim process commitment.

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_TRIMPROCESSCOMMITMENT](ns-d3dkmthk-_d3dkmt_trimprocesscommitment.md) structure.

## -returns

Returns NTSTATUS.

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

## -remarks

## -see-also

