---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
author: windows-driver-content
description: The EvtNetAdapterReceiveScalingSetIndirectionEntries callback function is implemented by the client driver to perform moves of individual receive side scaling (RSS) indirection table entries to new processors.
ms.assetid: 7483bad1-4ec0-44aa-bd4c-16d32e44bb70
ms.author: windowsdriverdev
ms.date: 03/07/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netreceivescaling.h
req.include-header:
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
-	netreceivescaling.h
apiname: 
-	EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES callback function

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The *EvtNetAdapterReceiveScalingSetIndirectionEntries* callback function is implemented by the client driver to perform moves of individual receive side scaling (RSS) indirection table entries to new processors.

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES EvtNetAdapterReceiveScalingSetIndirectionEntries; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetIndirectionEntries 
(
	_In_	NETADAPTER											Adapter,
	_In_	PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES	IndirectionEntries
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
```

## -parameters

### -param Adapter: 
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param IndirectionEntries: 
A pointer to a [NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md) structure that represents the indirection table.

## -returns
Returns STATUS_SUCCESS if the move operations were successful. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks
Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** from their *[EvtNetAdapterSetCapabilities](../netadapter/nc-netadapter-evt_net_adapter_set_capabilities.md)* callback function.

The minimum NetAdapterCx version for *EvtNetAdapterReceiveScalingSetIndirectionEntries* is 1.2.

### Example

NetAdapterCx invokes a client driver's *EvtNetAdapterReceiveScalingSetIndirectionEntries* callback when it needs to rebalance processor workloads for RSS. In this callback, you typically compute a new processor number based on each entry's receive queue ID, then set the new result to your hardware's RSS indirection table. You can retrieve the receive queue ID from the queue's context space. 

go to index, change it to the queue we said to change it to. Can fail individual index entries. entries each have the rx queue id. it could be that drivers might assign their own IDs to each queue. 

```C++
NTSTATUS
MyEvtAdapterReceiveScalingSetIndirectionEntries(
	_In_	NETADAPTER											netAdapter,
	_In_	NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES*	indirectionEntries
)
{
	
}
```

## -see-also
[NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md)

[NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling)