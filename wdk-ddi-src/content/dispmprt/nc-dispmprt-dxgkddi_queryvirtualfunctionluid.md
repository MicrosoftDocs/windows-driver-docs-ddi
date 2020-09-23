---
UID: NC:dispmprt.DXGKDDI_QUERYVIRTUALFUNCTIONLUID
title: DXGKDDI_QUERYVIRTUALFUNCTIONLUID
description: Queries for a virtual function's locally unique identifier.
tech.root: display
ms.assetid: 9d908fbf-4d2e-4099-b0d5-12cdb5014d61
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_QUERYVIRTUALFUNCTIONLUID callback function"]
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_QUERYVIRTUALFUNCTIONLUID
 - dispmprt/DXGKDDI_QUERYVIRTUALFUNCTIONLUID
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_QUERYVIRTUALFUNCTIONLUID
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_QUERYVIRTUALFUNCTIONLUID callback function


## -description

Queries for a virtual function's locally unique identifier.

## -parameters

### -param Context

A handle to the context.

### -param pArgs

Pointer to a DXGKARG_QUERYVIRTUALFUNCTIONLUID structure.

## -prototype

```
//Declaration

DXGKDDI_QUERYVIRTUALFUNCTIONLUID DxgkddiQueryvirtualfunctionluid; 

// Definition

VOID DxgkddiQueryvirtualfunctionluid 
(
	HANDLE Context
	DXGKARG_QUERYVIRTUALFUNCTIONLUID * pArgs
)
{...}

```

## -remarks

## -see-also

