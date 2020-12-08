---
UID: NC:d3dkmddi.DXGKCB_ACQUIREHANDLEDATA
title: DXGKCB_ACQUIREHANDLEDATA (d3dkmddi.h)
description: Acquires a resource handle.
ms.date: 10/19/2018
keywords: ["DXGKCB_ACQUIREHANDLEDATA callback function"]
req.header: d3dkmddi.h
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
 - DXGKCB_ACQUIREHANDLEDATA
 - d3dkmddi/DXGKCB_ACQUIREHANDLEDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ACQUIREHANDLEDATA
dev_langs:
 - c++
---

# DXGKCB_ACQUIREHANDLEDATA callback function


## -description

Implemented by the client driver to acquire a resource handle.

## -returns

Returns VOID.

## -prototype

```cpp
//Declaration

DXGKCB_ACQUIREHANDLEDATA DxgkcbAcquirehandledata; 

// Definition

VOID * DxgkcbAcquirehandledata 
(
)
{...}

```

