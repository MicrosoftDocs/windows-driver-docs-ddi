---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
title: EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
description: The EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP callback function is reserved for system use. Do not implement this callback in your code.
tech.root: netvista
ms.assetid: 65acce86-1aa2-463e-be4f-12db185f38e9
ms.date: 03/06/2018
ms.topic: callback
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
product:
-	Windows
targetos: Windows
---

# EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP callback function

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP* callback function is reserved for system use. Do not implement this callback in your code.

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP EvtNetAdapterCreateRssqueueGroup; 

// Definition

NTSTATUS EvtNetAdapterCreateRssqueueGroup 
(
	_In_	NETADAPTER				Adapter,
	_Inout_	PNETRSSQUEUEGROUP_INIT	RssQueueGroupInit
)
{...}

typedef EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP *PFN_NET_ADAPTER_CREATE_RSSQUEUE_GROUP;
```

## -parameters

### -param Adapter 
Reserved.

### -param RssQueueGroupInit 
Reserved.

## -returns
Reserved for system use.

## -remarks

## -see-also

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
