---
UID: NC:ntddk.PPHYSICAL_COUNTER_OVERFLOW_HANDLER
title: PPHYSICAL_COUNTER_OVERFLOW_HANDLER
author: windows-driver-content
description: 
tech.root:
ms.assetid: 49f5213b-3b7e-4bdc-9f4d-16c06e602fba
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
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
 - PPHYSICAL_COUNTER_OVERFLOW_HANDLER
product: Windows
targetos: Windows
---

# PPHYSICAL_COUNTER_OVERFLOW_HANDLER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PPHYSICAL_COUNTER_OVERFLOW_HANDLER PphysicalCounterOverflowHandler; 

// Definition

VOID PphysicalCounterOverflowHandler 
(
	ULONGLONG OverflowBits
	HANDLE OwningHandle
)
{...}

```

## -parameters

### -param OverflowBits: 
### -param OwningHandle: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also