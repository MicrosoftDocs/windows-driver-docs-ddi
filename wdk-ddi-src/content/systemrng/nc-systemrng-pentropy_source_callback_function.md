---
UID: NC:systemrng.PENTROPY_SOURCE_CALLBACK_FUNCTION
title: PENTROPY_SOURCE_CALLBACK_FUNCTION
author: windows-driver-content
description: 
ms.assetid: e9ed974c-3854-4644-8ad9-9f694082698e
ms.date: 
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	systemrng.h
api_name: 
-	PENTROPY_SOURCE_CALLBACK_FUNCTION
product:
-	Windows
targetos: Windows
---

# PENTROPY_SOURCE_CALLBACK_FUNCTION callback function

## -description


## -prototype

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

## -parameters

### -param hEntropySource: 
### -param context: 



## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
