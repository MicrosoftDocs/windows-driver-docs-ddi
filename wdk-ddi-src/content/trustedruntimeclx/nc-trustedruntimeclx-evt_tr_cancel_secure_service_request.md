---
UID: NC:trustedruntimeclx.EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
title: EVT_TR_CANCEL_SECURE_SERVICE_REQUEST (trustedruntimeclx.h)
description: 
ms.assetid: 5a3bb56d-cde5-4776-84af-ed1264577a51
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "trustedruntimeclx/EVT_TR_CANCEL_SECURE_SERVICE_REQUEST"
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
- EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_CANCEL_SECURE_SERVICE_REQUEST callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_CANCEL_SECURE_SERVICE_REQUEST EvtTrCancelSecureServiceRequest; 

// Definition

VOID EvtTrCancelSecureServiceRequest 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT SessionContext
	PVOID RequestHandle
	PVOID * RequestContext
)
{...}

```

## -parameters

### -param ServiceDevice: 
### -param SessionContext: 
### -param RequestHandle: 
### -param RequestContext: 



## -returns



## -remarks




## -see-also
