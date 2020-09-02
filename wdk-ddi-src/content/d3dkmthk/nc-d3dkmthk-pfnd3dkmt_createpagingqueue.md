---
UID: NC:d3dkmthk.PFND3DKMT_CREATEPAGINGQUEUE
title: PFND3DKMT_CREATEPAGINGQUEUE (d3dkmthk.h)
description: The PFND3DKMT_CREATEPAGINGQUEUE callback function creates a paging queue.
ms.assetid: c0aa3399-4862-4836-a183-141caa8264d4
ms.date: 10/19/2018
keywords: ["PFND3DKMT_CREATEPAGINGQUEUE callback function"]
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
 - PFND3DKMT_CREATEPAGINGQUEUE
 - d3dkmthk/PFND3DKMT_CREATEPAGINGQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEPAGINGQUEUE
dev_langs:
 - c++
---

# PFND3DKMT_CREATEPAGINGQUEUE callback function


## -description

The PFND3DKMT_CREATEPAGINGQUEUE callback function creates a paging queue.

## -parameters

### -param Arg1

Pointer to a [D3DKMT_CREATEPAGINGQUEUE](ns-d3dkmthk-_d3dkmt_createpagingqueue.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

PFND3DKMT_CREATEPAGINGQUEUE Pfnd3dkmtCreatepagingqueue; 

// Definition

NTSTATUS Pfnd3dkmtCreatepagingqueue 
(
	D3DKMT_CREATEPAGINGQUEUE *
)
{...}

```

