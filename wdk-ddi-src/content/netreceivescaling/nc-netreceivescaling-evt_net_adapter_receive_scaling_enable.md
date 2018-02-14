---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
title: EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
author: windows-driver-content
description: 
ms.assetid: a37af139-8c98-4733-b2d2-cb0c9d67de35
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
-	EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE EvtNetAdapterReceiveScalingEnable; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingEnable 
(
	NETADAPTER Adapter
)
{...}

EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE *PFN_NET_ADAPTER_RECEIVE_SCALING_ENABLE


```

## -parameters

### -param Adapter: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also