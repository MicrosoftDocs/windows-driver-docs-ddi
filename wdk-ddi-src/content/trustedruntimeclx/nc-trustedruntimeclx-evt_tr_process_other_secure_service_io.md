---
UID: NC:trustedruntimeclx.EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
title: EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
author: windows-driver-content
description: 
ms.assetid: 73774bab-6134-40b9-97f7-5ee28aa0929f
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
-	EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO
product: Windows
targetos: Windows
---

# EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_TR_PROCESS_OTHER_SECURE_SERVICE_IO EvtTrProcessOtherSecureServiceIo; 

// Definition

VOID EvtTrProcessOtherSecureServiceIo 
(
	WDFDEVICE ServiceDevice
	WDFOBJECT SessionContext
	WDFREQUEST Request
)
{...}

```

## -parameters

### -param ServiceDevice: 
### -param SessionContext: 
### -param Request: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also