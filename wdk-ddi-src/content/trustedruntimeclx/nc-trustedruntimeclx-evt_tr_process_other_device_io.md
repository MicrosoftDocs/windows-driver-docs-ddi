---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_OTHER_DEVICE_IO
title: EVT_TR_PROCESS_OTHER_DEVICE_IO
author: windows-driver-content
description: 
ms.assetid: 33c1d7c7-75bc-4a1d-a7b4-d85180224a68
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
-	EVT_TR_PROCESS_OTHER_DEVICE_IO
product: Windows
targetos: Windows
---

# EVT_TR_PROCESS_OTHER_DEVICE_IO callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also