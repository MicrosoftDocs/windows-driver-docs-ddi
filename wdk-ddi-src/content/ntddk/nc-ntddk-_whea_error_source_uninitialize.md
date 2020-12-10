---
UID: NC:ntddk._WHEA_ERROR_SOURCE_UNINITIALIZE
title: _WHEA_ERROR_SOURCE_UNINITIALIZE
description: 
tech.root: whea
ms.date: 08/19/2019
keywords: ["WHEA_ERROR_SOURCE_UNINITIALIZE callback function"]
req.header: ntddk.h
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
ms.custom: 19H1
f1_keywords:
 - _WHEA_ERROR_SOURCE_UNINITIALIZE
 - ntddk/_WHEA_ERROR_SOURCE_UNINITIALIZE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SOURCE_UNINITIALIZE
product:
 - Windows
---

# _WHEA_ERROR_SOURCE_UNINITIALIZE callback function


## -description

Implemented by the client driver to ...

## -parameters

### -param Context: 

## -prototype

```
//Declaration

_WHEA_ERROR_SOURCE_UNINITIALIZE WheaErrorSourceUninitialize; 

// Definition

VOID WheaErrorSourceUninitialize 
(
	PVOID Context
)
{...}

```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.

## -see-also

