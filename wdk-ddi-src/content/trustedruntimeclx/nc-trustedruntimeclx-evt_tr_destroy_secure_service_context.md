---
UID: NC:trustedruntimeclx.EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT
title: EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT (trustedruntimeclx.h)
description: 
ms.assetid: 29b30f6b-8050-41ce-9dbb-2f0bef850eff
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "trustedruntimeclx/EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT"
req.header: trustedruntimeclx.h
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
- trustedruntimeclx.h
api_name: 
- EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT callback function

## -description

 

## -syntax

```cpp
//Declaration

EVT_TR_DESTROY_SECURE_SERVICE_CONTEXT EvtTrDestroySecureServiceContext; 

// Definition

NTSTATUS EvtTrDestroySecureServiceContext 
(
	WDFDEVICE ServiceDevice
)
{...}

```

## -parameters

### -param ServiceDevice: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
