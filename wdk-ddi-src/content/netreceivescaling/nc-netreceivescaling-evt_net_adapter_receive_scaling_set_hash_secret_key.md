---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
author: windows-driver-content
description: 
ms.assetid: 9144fad7-c6d6-4d67-9ad7-45e9a0cf31f6
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
-	EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY EvtNetAdapterReceiveScalingSetHashSecretKey; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetHashSecretKey 
(
	NETADAPTER Adapter
	PCNET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY HashSecretKey
)
{...}

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY


```

## -parameters

### -param Adapter: 
### -param HashSecretKey: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also