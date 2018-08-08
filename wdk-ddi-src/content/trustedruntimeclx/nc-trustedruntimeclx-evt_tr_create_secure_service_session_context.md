---
UID: NC:trustedruntimeclx.EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
title: EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
author: windows-driver-content
description: 
ms.assetid: 398accdf-300c-43d5-b460-f87f83c6edfc
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT
product: Windows
targetos: Windows
---

# EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_TR_CREATE_SECURE_SERVICE_SESSION_CONTEXT EvtTrCreateSecureServiceSessionContext; 

// Definition

NTSTATUS EvtTrCreateSecureServiceSessionContext 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT * SessionContextObject
)
{...}

```

## -parameters

### -param ServiceDevice: 
### -param SessionContextObject: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also