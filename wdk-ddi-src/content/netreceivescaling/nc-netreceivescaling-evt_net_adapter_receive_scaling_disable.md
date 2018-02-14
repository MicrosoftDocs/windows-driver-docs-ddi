---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
title: EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
author: windows-driver-content
description: 
ms.assetid: 3c249ff6-2a88-4b73-9f04-b3be1a2996d9
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netreceivescaling.h
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netreceivescaling.h
apiname: 
-	EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE EvtNetAdapterReceiveScalingDisable; 

// Definition

VOID EvtNetAdapterReceiveScalingDisable 
(
	NETADAPTER Adapter
)
{...}

EVT_NET_ADAPTER_RECEIVE_SCALING_DISABLE *PFN_NET_ADAPTER_RECEIVE_SCALING_DISABLE


```

## -parameters

### -param Adapter: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also