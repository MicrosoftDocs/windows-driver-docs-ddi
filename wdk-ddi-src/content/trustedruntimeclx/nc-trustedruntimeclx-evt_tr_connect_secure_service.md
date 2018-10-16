---
UID: NC:trustedruntimeclx.EVT_TR_CONNECT_SECURE_SERVICE
title: EVT_TR_CONNECT_SECURE_SERVICE
author: windows-driver-content
description: 
ms.assetid: 68fa7c1e-e03f-46b5-8373-391bb6dd330d
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
-	EVT_TR_CONNECT_SECURE_SERVICE
product:
-	Windows
targetos: Windows
---

# EVT_TR_CONNECT_SECURE_SERVICE callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_CONNECT_SECURE_SERVICE EvtTrConnectSecureService; 

// Definition

NTSTATUS EvtTrConnectSecureService 
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
