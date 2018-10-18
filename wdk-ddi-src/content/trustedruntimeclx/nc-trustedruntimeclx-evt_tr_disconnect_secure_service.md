---
UID: NC:trustedruntimeclx.EVT_TR_DISCONNECT_SECURE_SERVICE
title: EVT_TR_DISCONNECT_SECURE_SERVICE
author: windows-driver-content
description: 
ms.assetid: f0bcdca4-bbbd-4ec5-88ce-dc8b68fcbd31
ms.date: 
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
-	EVT_TR_DISCONNECT_SECURE_SERVICE
product:
-	Windows
targetos: Windows
---

# EVT_TR_DISCONNECT_SECURE_SERVICE callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_DISCONNECT_SECURE_SERVICE EvtTrDisconnectSecureService; 

// Definition

NTSTATUS EvtTrDisconnectSecureService 
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
