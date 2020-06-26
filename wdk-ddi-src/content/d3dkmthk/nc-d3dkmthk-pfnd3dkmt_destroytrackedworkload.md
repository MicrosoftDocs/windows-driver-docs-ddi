---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYTRACKEDWORKLOAD
title: PFND3DKMT_DESTROYTRACKEDWORKLOAD (d3dkmthk.h)
description: Destroys a tracked workload.
ms.assetid: 0b1d1f0b-bb03-45d5-9c8d-3e1b0354c074
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYTRACKEDWORKLOAD callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_DESTROYTRACKEDWORKLOAD"
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmthk.h
api_name: 
- PFND3DKMT_DESTROYTRACKEDWORKLOAD
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3DKMT_DESTROYTRACKEDWORKLOAD callback function

## -description

Destroys a tracked workload.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYTRACKEDWORKLOAD Pfnd3dkmtDestroytrackedworkload; 

// Definition

NTSTATUS Pfnd3dkmtDestroytrackedworkload 
(
	D3DKMT_DESTROYTRACKEDWORKLOAD *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_DESTROYTRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_destroytrackedworkload.md) structure to destroy a tracked workload.

## -returns

Returns NTSTATUS.

## -remarks


## -see-also
