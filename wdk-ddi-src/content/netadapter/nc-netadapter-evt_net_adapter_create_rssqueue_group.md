---
UID: NC:netadapter.EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
title: EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
author: windows-driver-content
description: 
ms.assetid: 65acce86-1aa2-463e-be4f-12db185f38e9
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP EvtNetAdapterCreateRssqueueGroup; 

// Definition

NTSTATUS EvtNetAdapterCreateRssqueueGroup 
(
	NETADAPTER Adapter
	PNETRSSQUEUEGROUP_INIT RssQueueGroupInit
)
{...}

EVT_NET_ADAPTER_CREATE_RSSQUEUE_GROUP *PFN_NET_ADAPTER_CREATE_RSSQUEUE_GROUP


```

## -parameters

### -param Adapter: 
### -param RssQueueGroupInit: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also