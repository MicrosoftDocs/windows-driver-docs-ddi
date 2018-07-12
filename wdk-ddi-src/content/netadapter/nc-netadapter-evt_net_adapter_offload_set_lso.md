---
UID: NC:netadapter.EVT_NET_ADAPTER_OFFLOAD_SET_LSO
title: EVT_NET_ADAPTER_OFFLOAD_SET_LSO
author: windows-driver-content
description: 
ms.assetid: 7c11be49-4d85-49c4-9416-47da1214fc1b
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
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
-	netadapter.h
api_name: 
-	EVT_NET_ADAPTER_OFFLOAD_SET_LSO
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_OFFLOAD_SET_LSO callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_LSO EvtNetAdapterOffloadSetLso; 

// Definition

VOID EvtNetAdapterOffloadSetLso 
(
	NETADAPTER Adapter
	PNET_ADAPTER_OFFLOAD_LSO_CAPABILITIES ActiveCapabilities
)
{...}

```

## -parameters

### -param Adapter: 
### -param ActiveCapabilities: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also