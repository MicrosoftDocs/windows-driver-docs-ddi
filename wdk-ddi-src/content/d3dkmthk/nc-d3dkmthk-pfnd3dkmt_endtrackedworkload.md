---
UID: NC:d3dkmthk.PFND3DKMT_ENDTRACKEDWORKLOAD
title: PFND3DKMT_ENDTRACKEDWORKLOAD (d3dkmthk.h)
description: Indicates that the tracked workload commands are done.
ms.assetid: ebd36bfd-86a7-45f1-8b3f-2f9f639aa334
ms.date: 10/19/2018
keywords: ["PFND3DKMT_ENDTRACKEDWORKLOAD callback function"]
f1_keywords:
 - "d3dkmthk/PFND3DKMT_ENDTRACKEDWORKLOAD"
 - "PFND3DKMT_ENDTRACKEDWORKLOAD"
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
- PFND3DKMT_ENDTRACKEDWORKLOAD
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3DKMT_ENDTRACKEDWORKLOAD callback function

## -description

Indicates that the tracked workload commands are done.

## -prototype

```cpp
//Declaration

PFND3DKMT_ENDTRACKEDWORKLOAD Pfnd3dkmtEndtrackedworkload; 

// Definition

NTSTATUS Pfnd3dkmtEndtrackedworkload 
(
	D3DKMT_ENDTRACKEDWORKLOAD *
)
{...}

```

## -parameters

### -param Arg1

Pointer to a [D3DKMT_ENDTRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_endtrackedworkload.md) structure to end the tracked workload.

## -returns

Returns NTSTATUS that.

## -remarks




## -see-also
