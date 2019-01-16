---
UID: NC:ntddk.PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
title: PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
author: windows-driver-content
description: 
tech.root:
ms.assetid: 0166926b-64aa-48a1-a8a5-c52a4f63c1e4
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
 - PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER
product: Windows
targetos: Windows
---

# PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PPHYSICAL_COUNTER_EVENT_BUFFER_OVERFLOW_HANDLER PphysicalCounterEventBufferOverflowHandler; 

// Definition

VOID PphysicalCounterEventBufferOverflowHandler 
(
	PVOID EventBuffer
	SIZE_T EntrySize
	SIZE_T NumberOfEntries
	HANDLE OwningHandle
)
{...}

```

## -parameters

### -param EventBuffer: 
### -param EntrySize: 
### -param NumberOfEntries: 
### -param OwningHandle: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also