---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYPAGINGQUEUE
title: PFND3DKMT_DESTROYPAGINGQUEUE (d3dkmthk.h)
description: The PFND3DKMT_DESTROYPAGINGQUEUE callback function destroys paging queue.
ms.date: 10/19/2018
keywords: ["PFND3DKMT_DESTROYPAGINGQUEUE callback function"]
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
 - PFND3DKMT_DESTROYPAGINGQUEUE
 - d3dkmthk/PFND3DKMT_DESTROYPAGINGQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYPAGINGQUEUE
dev_langs:
 - c++
---

# PFND3DKMT_DESTROYPAGINGQUEUE callback function


## -description

The PFND3DKMT_DESTROYPAGINGQUEUE callback function destroys paging queue.

## -parameters

### -param Arg1

Pointer to a [D3DDDI_DESTROYPAGINGQUEUE](../d3dukmdt/ns-d3dukmdt-d3dddi_destroypagingqueue.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_DESTROYPAGINGQUEUE Pfnd3dkmtDestroypagingqueue; 

// Definition

NTSTATUS Pfnd3dkmtDestroypagingqueue 
(
	D3DDDI_DESTROYPAGINGQUEUE *
)
{...}

```

