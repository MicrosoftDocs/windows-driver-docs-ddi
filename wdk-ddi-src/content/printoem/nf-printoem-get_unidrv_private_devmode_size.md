---
UID: NF:printoem.GET_UNIDRV_PRIVATE_DEVMODE_SIZE
title: GET_UNIDRV_PRIVATE_DEVMODE_SIZE macro (printoem.h)
description: Returns PScript5's private DEVMODE structure to allow its plugins to determine its size.
ms.date: 08/12/2022
keywords: ["GET_UNIDRV_PRIVATE_DEVMODE_SIZE macro"]
ms.keywords: GET_UNIDRV_PRIVATE_DEVMODE_SIZE
req.header: printoem.h
req.include-header: Printoem.h
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
tech.root: print
f1_keywords:
 - GET_UNIDRV_PRIVATE_DEVMODE_SIZE
 - printoem/GET_UNIDRV_PRIVATE_DEVMODE_SIZE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - GET_UNIDRV_PRIVATE_DEVMODE_SIZE
product:
 - Windows
---

# GET_UNIDRV_PRIVATE_DEVMODE_SIZE macro

## -description

Returns PScript5's private DEVMODE structure to allow its plugins to determine its size.

## -parameters

### -param pdm

Contains the size of the private **DEVMODE** structure.

## -remarks

```cpp
#define GET_UNIDRV_PRIVATE_DEVMODE_SIZE(pdm) \
    ( ( (pdm)->dmDriverExtra > (FIELD_OFFSET(UNIDRV_PRIVATE_DEVMODE, wSize) + sizeof(WORD)) ) ? \
        ((PUNIDRV_PRIVATE_DEVMODE)((PBYTE)(pdm) + (pdm)->dmSize))->wSize : 0 )
```
