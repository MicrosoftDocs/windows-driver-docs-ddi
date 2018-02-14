---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
author: windows-driver-content
description: 
ms.assetid: 7483bad1-4ec0-44aa-bd4c-16d32e44bb70
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
-	EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES EvtNetAdapterReceiveScalingSetIndirectionEntries; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetIndirectionEntries 
(
	NETADAPTER Adapter
	PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES IndirectionEntries
)
{...}

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES


```

## -parameters

### -param Adapter: 
### -param IndirectionEntries: 



## -returns

Returns NTSTATUS that ...
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also