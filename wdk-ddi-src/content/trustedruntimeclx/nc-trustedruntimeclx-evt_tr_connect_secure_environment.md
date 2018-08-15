---
UID: NC:trustedruntimeclx.EVT_TR_CONNECT_SECURE_ENVIRONMENT
title: EVT_TR_CONNECT_SECURE_ENVIRONMENT
author: windows-driver-content
description: 
ms.assetid: 4fad5c91-d436-46cd-b3ca-41b48b718506
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
-	EVT_TR_CONNECT_SECURE_ENVIRONMENT
product:
-	Windows
targetos: Windows
---

# EVT_TR_CONNECT_SECURE_ENVIRONMENT callback function

## -description

 

## -prototype

```
//Declaration

EVT_TR_CONNECT_SECURE_ENVIRONMENT EvtTrConnectSecureEnvironment; 

// Definition

NTSTATUS EvtTrConnectSecureEnvironment 
(
	WDFDEVICE MasterDevice
)
{...}

```

## -parameters

### -param MasterDevice: 



## -returns


Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also