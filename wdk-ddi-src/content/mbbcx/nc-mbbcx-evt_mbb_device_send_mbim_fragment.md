---
UID: NC:mbbcx.EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT
title: EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT
author: windows-driver-content
description: 
ms.assetid: 16a6dd6c-b8df-41a9-bb93-34ae1c085eb4
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
-	EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT
product: Windows
targetos: Windows
---

# EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT EvtMbbDeviceSendMbimFragment; 

// Definition

VOID EvtMbbDeviceSendMbimFragment 
(
	WDFDEVICE Device
	MBBREQUEST SendRequest
)
{...}

```

## -parameters

### -param Device: 
### -param SendRequest: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also