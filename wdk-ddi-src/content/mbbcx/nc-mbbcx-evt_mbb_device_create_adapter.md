---
UID: NC:mbbcx.EVT_MBB_DEVICE_CREATE_ADAPTER
title: EVT_MBB_DEVICE_CREATE_ADAPTER
author: windows-driver-content
description: 
ms.assetid: db841566-dd24-4687-b00c-1bf2a22f4243
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: mbbcx.h
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
-	mbbcx.h
api_name: 
-	EVT_MBB_DEVICE_CREATE_ADAPTER
product: Windows
targetos: Windows
---

# EVT_MBB_DEVICE_CREATE_ADAPTER callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_MBB_DEVICE_CREATE_ADAPTER EvtMbbDeviceCreateAdapter; 

// Definition

NTSTATUS EvtMbbDeviceCreateAdapter 
(
	WDFDEVICE Device
	PNETADAPTER_INIT AdapterInit
)
{...}

```

## -parameters

### -param Device: 
### -param AdapterInit: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also