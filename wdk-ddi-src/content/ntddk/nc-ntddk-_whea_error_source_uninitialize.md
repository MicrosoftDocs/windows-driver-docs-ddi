---
UID: NC:ntddk._WHEA_ERROR_SOURCE_UNINITIALIZE
title: _WHEA_ERROR_SOURCE_UNINITIALIZE
author: windows-driver-content
description: 
tech.root:
ms.assetid: 4139dad8-6a00-44b0-8b2f-1bcc354169f1
ms.author: windowsdriverdev
ms.date: 08/19/2019
f1_keywords:
 - "ntddk/_WHEA_ERROR_SOURCE_UNINITIALIZE"
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
targetos: Windows
ms.custom: 19H1
---

# _WHEA_ERROR_SOURCE_UNINITIALIZE callback function

## -description

Implemented by the client driver to ... 

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

## -parameters

### -param Context: 



## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
