---
UID: NC:trustedruntimeclx.EVT_TR_ENUMERATE_SECURE_SERVICES
title: EVT_TR_ENUMERATE_SECURE_SERVICES (trustedruntimeclx.h)
description: 
ms.assetid: 23793977-ce47-48ab-abf8-2b02ebd3bdd3
ms.date: 10/19/2018
ms.topic: callback
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	trustedruntimeclx.h
api_name: 
-	EVT_TR_ENUMERATE_SECURE_SERVICES
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_ENUMERATE_SECURE_SERVICES callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_ENUMERATE_SECURE_SERVICES EvtTrEnumerateSecureServices; 

// Definition

NTSTATUS EvtTrEnumerateSecureServices 
(
	WDFDEVICE MasterDevice
	ULONG Index
	PUCHAR SecureServiceDescription
	ULONG * DescriptionSize
)
{...}

```

## -parameters

### -param MasterDevice: 
### -param Index: 
### -param SecureServiceDescription: 
### -param DescriptionSize: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
