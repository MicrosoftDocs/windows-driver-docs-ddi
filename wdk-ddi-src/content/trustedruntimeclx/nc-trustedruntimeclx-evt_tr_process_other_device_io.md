---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_OTHER_DEVICE_IO
title: EVT_TR_PROCESS_OTHER_DEVICE_IO
description: 
ms.assetid: 33c1d7c7-75bc-4a1d-a7b4-d85180224a68
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
-	EVT_TR_PROCESS_OTHER_DEVICE_IO
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# EVT_TR_PROCESS_OTHER_DEVICE_IO callback function

## -description

 

## -prototype

```cpp
//Declaration

EVT_TR_PROCESS_OTHER_DEVICE_IO EvtTrProcessOtherDeviceIo; 

// Definition

VOID EvtTrProcessOtherDeviceIo 
(
	WDFDEVICE MasterDevice
	WDFREQUEST Request
)
{...}

```

## -parameters

### -param MasterDevice: 
### -param Request: 



## -returns



## -remarks




## -see-also
