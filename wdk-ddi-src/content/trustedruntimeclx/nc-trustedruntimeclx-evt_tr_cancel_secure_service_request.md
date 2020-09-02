---
UID: NC:trustedruntimeclx.EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
title: EVT_TR_CANCEL_SECURE_SERVICE_REQUEST (trustedruntimeclx.h)
description: 
ms.assetid: 5a3bb56d-cde5-4776-84af-ed1264577a51
ms.date: 10/19/2018
keywords: ["EVT_TR_CANCEL_SECURE_SERVICE_REQUEST callback function"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
 - trustedruntimeclx/EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - trustedruntimeclx.h
api_name:
 - EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
---

# EVT_TR_CANCEL_SECURE_SERVICE_REQUEST callback function


## -description

## -parameters

### -param ServiceDevice: 

### -param SessionContext: 

### -param RequestHandle: 

### -param RequestContext: 

## -syntax

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

## -remarks

## -see-also

