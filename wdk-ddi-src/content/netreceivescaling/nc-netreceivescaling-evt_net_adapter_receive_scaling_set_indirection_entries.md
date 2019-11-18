---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES (netreceivescaling.h)
description: The EvtNetAdapterReceiveScalingSetIndirectionEntries callback function is implemented by the client driver to perform moves of individual receive side scaling (RSS) indirection table entries to new processors.
tech.root: netvista
ms.assetid: 7483bad1-4ec0-44aa-bd4c-16d32e44bb70
ms.date: 03/07/2018
ms.topic: callback
f1_keywords:
 - "netreceivescaling/EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE"
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
- apiref
apitype: 
- UserDefined
apilocation: 
- netreceivescaling.h
apiname: 
- EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
product:
- Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES callback function

## -description


The *EvtNetAdapterReceiveScalingSetIndirectionEntries* callback function is implemented by the client driver to perform moves of receive side scaling (RSS) indirection table entries to new receive queues.

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES EvtNetAdapterReceiveScalingSetIndirectionEntries; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetIndirectionEntries 
(
	_In_	NETADAPTER											Adapter,
	_Inout_	NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES *	IndirectionEntries
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES
```

## -parameters

### -param Adapter 

The NETADAPTER object the client driver obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param IndirectionEntries 

A pointer to a [**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md) structure that represents the indirection table.

## -returns

Returns STATUS_SUCCESS if the move operations were successful. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [**NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES**](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [**NetAdapterSetReceiveScalingCapabilities**](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

When a protocol driver needs to rebalance processor workload in RSS, it first calculates a new mapping for each indirection table entry to a new processor. Then the protocol passes this information to NetAdapterCx, which internally maps processor numbers to NIC receive queue IDs. NetAdapterCx stores the new indirection table, with entries mapped to receive queue IDs, in a [**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md) structure and passes this structure to the NIC client driver when it invokes the driver's *EvtNetAdapterReceiveScalingSetIndirectionEntries* callback function. 

In this callback, client drivers move each entry in their NIC's indirection table to the specified receive queue. Each [**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md) structure in the **NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES** array contains the hash index for that entry in the table, the new receive queue to which to assign the entry, and a status field indicating if that individual move succeeded or not. 

The method of assigning index entries to hardware receive queues depends on the design of each NIC. For example, some NIC client drivers might assign their own IDs to each receive queue that are different from the NetAdapterCx-assigned IDs, so they would have to first translate the provided queue IDs to their own queue IDs before reassigning indirection table entries. Other NICs might have a compressed indirection table that differs in size from the system-maintained indirection table, so client drivers of those NICs would need to calculate the correct index into their hardware's indirection table when assigning entries. For a code sample of this second example, see the [Realtek Github sample driver](https://github.com/Microsoft/NetAdapter-Cx-Driver-Samples/tree/master/RtEthSample).



### Example

This simple example assumes a 1:1 ratio of receive queues to processors, so the NIC's indirection table is the same size as the system's indirection table.

```C++
NTSTATUS
MyEvtNetAdapterReceiveScalingSetIndirectionEntries(
	_In_ 	NETADAPTER   										Adapter,
    _Inout_ PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES 	IndirectionEntries
)
{

	// Get the adapter's context to retrieve the address of the hardware indirection table
	PMY_NET_ADAPTER_CONTEXT adapterContext = GetMyAdapterContext(Adapter);

	// Assign each indirection table entry to the specified receive queue
	for(size_t i = 0; i < IndirectionEntries->Count; i++)
	{
		// Get the queue ID from its context
		const ULONG queueId = GetMyRxQueueContext(IndirectionEntries->Entries[i].Queue)->QueueId;
		
		// Get the hash index for this entry
		const UINT32 index = IndirectionEntries->Entries[i].Index;

		// Assign the new queue ID for this index in the indirection table and record success
		IndirectionEntries->Entries[i].Status = MySetIndirectionTableEntry(adapterContext->HardwareInfo->RssIndirectionTable[index], 
	queueId
	);
	}

	return STATUS_SUCCESS;
}
```

## -see-also
[**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md)

[**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
