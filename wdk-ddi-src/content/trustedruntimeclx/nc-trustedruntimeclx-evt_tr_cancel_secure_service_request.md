---
UID: NC:trustedruntimeclx.EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
title: EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
author: windows-driver-content
description: 
ms.assetid: 5a3bb56d-cde5-4776-84af-ed1264577a51
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
-	EVT_TR_CANCEL_SECURE_SERVICE_REQUEST
product:
-	Windows
targetos: Windows
---

# EVT_TR_CANCEL_SECURE_SERVICE_REQUEST callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also