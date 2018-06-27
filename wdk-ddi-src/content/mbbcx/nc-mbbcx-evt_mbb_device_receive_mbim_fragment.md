---
UID: NC:mbbcx.EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT
title: EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT
author: windows-driver-content
description: 
ms.assetid: aaf0e1ca-600d-4912-93ae-10dc6d04dd7e
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
-	EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT
product: Windows
targetos: Windows
---

# EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT EvtMbbDeviceReceiveMbimFragment; 

// Definition

VOID EvtMbbDeviceReceiveMbimFragment 
(
	WDFDEVICE Device
	MBBREQUEST ReceiveRequest
)
{...}

```

## -parameters

### -param Device: 
### -param ReceiveRequest: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also