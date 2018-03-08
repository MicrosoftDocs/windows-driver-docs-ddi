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

The minimum NetAdapterCx version for **EVT_NET_ADAPTER_RECEIVE_SCALING_SET_INDIRECTION_ENTRIES** is 1.2.

### Example

NetAdapterCx invokes a client driver's *EvtNetAdapterReceiveScalingSetIndirectionEntries* callback when it needs to rebalance processor workloads for RSS. In this callback, you typically compute a new processor number based on each entry's receive queue ID, then set the new result to your hardware's RSS indirection table. You can retrieve the receive queue ID from the queue's context space. 

In this example, the **NETADAPTER** stores a copy of its indirection table in its context space, as well as an address to a struct containing the NIC's control registers. This struct then contains the hardware's indirection table. Details such as how to calculate the new processor number and the size of the hardware indirection table are based on the design of the NIC and how many RSS queues it has.

```C++
NTSTATUS
MyEvtAdapterReceiveScalingSetIndirectionEntries(
	_In_	NETADAPTER											netAdapter,
	_In_	NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES*	indirectionEntries
)
{
	// Get the adapter context
	PMY_ADAPTER_CONTEXT adapterContext = MyAdapterGetContext(netAdapter);

	// Loop over each indirection table entry
	for(size_t i = 0; i < indirectionEntries->Count; i++)
	{
		// Get the receive queue ID and indirection table hash index for this entry
		const ULONG queueId = MyGetRxQueueContext(indirectionEntries->Entries[i].Queue)->QueueId;
		const UINT32 index = indirectionEntries->Entries[i].Index;

		// Calculate new processor for this entry based on the queue ID and current index
		const size_t bit0 = index >> ...
		const size_t bit1 = bit0 + ...

		// Update the adapter's indirection table
		adapterContext->IndirectionTable[bit0] = queueId & 1 ? ...
		
		adapterContext->IndirectionTable[bit1] = queueId & 2 ? ...
	}

	// Update the hardware indirection table
	for(size_t i = 0; i < ARRAYSIZE(adapterContext->CtrlRegsAddress->IndirectionTable); i++)
	{
		adapterContext->CtrlRegsAddress->IndirectionTable[i] = adapterContext->IndirectionTable[i];
	}

	return STATUS_SUCCESS;
}
```

## -see-also
[NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md)

[NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling)