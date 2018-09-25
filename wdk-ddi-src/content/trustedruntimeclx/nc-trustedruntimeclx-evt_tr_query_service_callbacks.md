---
UID: NC:trustedruntimeclx.EVT_TR_QUERY_SERVICE_CALLBACKS
title: EVT_TR_QUERY_SERVICE_CALLBACKS
author: windows-driver-content
description: 
ms.assetid: 1c9369ed-3095-4119-a2ed-faa7cedd6d12
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
-	EVT_TR_QUERY_SERVICE_CALLBACKS
product:
-	Windows
targetos: Windows
---

# EVT_TR_QUERY_SERVICE_CALLBACKS callback function

## -description

 

## -prototype

```
//Declaration

EVT_TR_QUERY_SERVICE_CALLBACKS EvtTrQueryServiceCallbacks; 

// Definition

PTR_SECURE_SERVICE_CALLBACKS EvtTrQueryServiceCallbacks 
(
	WDFDEVICE MasterDevice
	LPGUID ServiceGuid
)
{...}

```

## -parameters

### -param MasterDevice: 
### -param ServiceGuid: 



## -returns

Returns PTR_SECURE_SERVICE_CALLBACKS.

## -remarks




## -see-also