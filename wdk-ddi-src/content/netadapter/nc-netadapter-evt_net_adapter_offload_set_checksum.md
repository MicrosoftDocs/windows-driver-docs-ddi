---
UID: NC:netadapter.EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
title: EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
author: windows-driver-content
description: 
ms.assetid: 054d73bb-6832-41f6-b654-89d29bbc1892
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
-	EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM EvtNetAdapterOffloadSetChecksum; 

// Definition

VOID EvtNetAdapterOffloadSetChecksum 
(
	NETADAPTER Adapter
	PNET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES ActiveCapabilities
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