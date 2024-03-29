---
UID: NC:systemrng.PENTROPY_SOURCE_CALLBACK_FUNCTION
title: PENTROPY_SOURCE_CALLBACK_FUNCTION (systemrng.h)
description: "Learn more about: PENTROPY_SOURCE_CALLBACK_FUNCTION callback function"
ms.date: 11/19/2020
keywords: ["PENTROPY_SOURCE_CALLBACK_FUNCTION callback function"]
req.header: systemrng.h
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
tech.root: treedrv
f1_keywords:
 - PENTROPY_SOURCE_CALLBACK_FUNCTION
 - systemrng/PENTROPY_SOURCE_CALLBACK_FUNCTION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - systemrng.h
api_name:
 - PENTROPY_SOURCE_CALLBACK_FUNCTION
---

# PENTROPY_SOURCE_CALLBACK_FUNCTION callback function

## -description

## -parameters

### -param hEntropySource

### -param context

## -returns

Return STATUS_SUCCESS if the operation succeeds.

Otherwise, return an appropriate NTSTATUS values error code.

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -syntax

```cpp
//Declaration

PENTROPY_SOURCE_CALLBACK_FUNCTION PentropySourceCallbackFunction;

// Definition

NTSTATUS PentropySourceCallbackFunction
(
    ENTROPY_SOURCE_HANDLE hEntropySource
    PVOID context
)
{...}

```

## -remarks

## -see-also
