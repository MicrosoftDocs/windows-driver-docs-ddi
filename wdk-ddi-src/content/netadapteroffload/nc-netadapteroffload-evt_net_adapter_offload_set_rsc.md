---
UID: NC:netadapteroffload.EVT_NET_ADAPTER_OFFLOAD_SET_RSC
title: EVT_NET_ADAPTER_OFFLOAD_SET_RSC (netadapteroffload.h)
author: windows-driver-content
description: 
tech.root:
ms.assetid: b23d877b-4f75-497b-8b2c-5082eaba2ba2
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
f1_keywords:
 - "netadapteroffload/EVT_NET_ADAPTER_OFFLOAD_SET_RSC"
req.header: netadapteroffload.h
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - netadapteroffload.h
api_name: 
 - EVT_NET_ADAPTER_OFFLOAD_SET_RSC
product: 
 - Windows
targetos: Windows
ms.custom: Vib
---

# EVT_NET_ADAPTER_OFFLOAD_SET_RSC callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_OFFLOAD_SET_RSC EvtNetAdapterOffloadSetRsc; 

// Definition

void EvtNetAdapterOffloadSetRsc 
(
	NETADAPTER Adapter
	NETOFFLOAD Offload
)
{...}

```

## -parameters

### -param Adapter: 
### -param Offload: 



## -returns

Returns void that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also