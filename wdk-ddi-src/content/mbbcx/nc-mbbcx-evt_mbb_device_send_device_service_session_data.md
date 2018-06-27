---
UID: NC:mbbcx.EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
title: EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
author: windows-driver-content
description: 
ms.assetid: ce977d52-cc00-472c-84f9-e3d7e9fe9778
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
-	EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
product: Windows
targetos: Windows
---

# EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA EvtMbbDeviceSendDeviceServiceSessionData; 

// Definition

VOID EvtMbbDeviceSendDeviceServiceSessionData 
(
	WDFDEVICE Device
	DSS_SESSION_ID SessionId
	WDFMEMORY Data
)
{...}

```

## -parameters

### -param Device: 
### -param SessionId: 
### -param Data: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also