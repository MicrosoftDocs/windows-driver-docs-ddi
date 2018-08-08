---
UID: NC:wdm.GET_UPDATED_BUS_RESOURCE
title: GET_UPDATED_BUS_RESOURCE
author: windows-driver-content
description: 
ms.assetid: d2624b1d-c2db-4240-ae78-1bda7efb8c7f
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdm.h
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
-	wdm.h
api_name: 
-	GET_UPDATED_BUS_RESOURCE
product: Windows
targetos: Windows
---

# GET_UPDATED_BUS_RESOURCE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

GET_UPDATED_BUS_RESOURCE GetUpdatedBusResource; 

// Definition

NTSTATUS GetUpdatedBusResource 
(
	PVOID Context
	PCM_RESOURCE_LIST * UpdatedResourceList
	PCM_RESOURCE_LIST * UpdatedTranslatedResourceList
)
{...}

```

## -parameters

### -param Context: 
### -param UpdatedResourceList: 
### -param UpdatedTranslatedResourceList: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also