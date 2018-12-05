---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_SECURE_SERVICE_REQUEST
title: EVT_TR_PROCESS_SECURE_SERVICE_REQUEST
author: windows-driver-content
description: 
ms.assetid: a79196b5-1c91-4b88-a6a7-8e5dc9814233
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
-	EVT_TR_PROCESS_SECURE_SERVICE_REQUEST
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_PROCESS_SECURE_SERVICE_REQUEST callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_PROCESS_SECURE_SERVICE_REQUEST EvtTrProcessSecureServiceRequest; 

// Definition

NTSTATUS EvtTrProcessSecureServiceRequest 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT SessionContext
	PVOID RequestHandle
	KPRIORITY Priority
	PTR_SERVICE_REQUEST Request
	ULONG Flags
	PULONG_PTR BytesWritten
	PVOID * RequestContext
)
{...}

```

## -parameters

### -param ServiceDevice: 
### -param SessionContext: 
### -param RequestHandle: 
### -param Priority: 
### -param Request: 
### -param Flags: 
### -param BytesWritten: 
### -param RequestContext: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
