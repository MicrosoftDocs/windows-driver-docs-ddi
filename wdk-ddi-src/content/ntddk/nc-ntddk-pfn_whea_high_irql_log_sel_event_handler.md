---
UID: NC:ntddk.PFN_WHEA_HIGH_IRQL_LOG_SEL_EVENT_HANDLER
title: PFN_WHEA_HIGH_IRQL_LOG_SEL_EVENT_HANDLER
author: windows-driver-content
description: 
tech.root:
ms.assetid: 32e3153b-8701-48ec-ae54-5f508593fd97
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
 - PFN_WHEA_HIGH_IRQL_LOG_SEL_EVENT_HANDLER
product: 
 - Windows
targetos: Windows
---

# PFN_WHEA_HIGH_IRQL_LOG_SEL_EVENT_HANDLER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_WHEA_HIGH_IRQL_LOG_SEL_EVENT_HANDLER PfnWheaHighIrqlLogSelEventHandler; 

// Definition

NTSTATUS PfnWheaHighIrqlLogSelEventHandler 
(
	PVOID Context
	PIPMI_OS_SEL_RECORD OsSelRecord
)
{...}

```

## -parameters

### -param Context: 
### -param OsSelRecord: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also