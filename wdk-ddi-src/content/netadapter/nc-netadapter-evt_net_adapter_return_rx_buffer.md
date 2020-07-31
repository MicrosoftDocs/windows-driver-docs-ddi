---
UID: NC:netadapter.EVT_NET_ADAPTER_RETURN_RX_BUFFER
title: EVT_NET_ADAPTER_RETURN_RX_BUFFER (netadapter.h)
description: Implement this optional callback function to perform cleanup on a receive buffer for which you previously specified manual fragment allocation and attachment.
tech.root: netvista
ms.assetid: E999C47A-CAE1-42AB-9900-4118EFFAEE0D
ms.date: 09/27/2019
keywords: ["EVT_NET_ADAPTER_RETURN_RX_BUFFER callback function"]
f1_keywords:
 - "netadapter/EVT_NET_ADAPTER_RETURN_RX_BUFFER"
 - "EVT_NET_ADAPTER_RETURN_RX_BUFFER"
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
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
- netadapter.h
api_name: 
- EVT_NET_ADAPTER_RETURN_RX_BUFFER
targetos: Windows
---

# EVT_NET_ADAPTER_RETURN_RX_BUFFER callback function

## -description

Implement this optional callback function to perform cleanup on a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) receive buffer for which you previously specified manual fragment allocation and attachment.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_RETURN_RX_BUFFER EvtNetAdapterReturnRxBuffer; 

// Definition

VOID EvtNetAdapterReturnRxBuffer 
(
	_In_	NETADAPTER							Adapter,
	_In_	NET_FRAGMENT_RETURN_CONTEXT_HANDLE	RxReturnContext
)
{...}

typedef EVT_NET_ADAPTER_RETURN_RX_BUFFER *PFN_NET_ADAPTER_RETURN_RX_BUFFER;
```

## -parameters

### -param Adapter 

The network adapter object that the client created in a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param RxBufferReturnContext 

A pointer to a driver-allocated context space structure.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md) structure and then calling [**NetAdapterSetDatapathCapabilities**](nf-netadapter-netadaptersetdatapathcapabilities.md). Client drivers typically call **NetAdapterSetDatapathCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

This callback function is optional unless the net adapter client driver initializes its [**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md) structure using the [**NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED**](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md) method. By using this initialization method, the driver tells the operating system that it is managing allocation and attachment of [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md) receive buffers manually, so it must provide this callback function in this case for the operating system to invoke once the system is finished with the buffer.

### Example

In this callback function, the client driver can perform whatever cleanup or follow-up actions it needs now that the operating system has finished with this receive buffer. In the following example, the return context contains a member to track the number of indicated packets, as well as a memory object used for a lookaside buffer during receive processing. Error handling has been left out for clarity.

```c++
VOID
MyReturnRxBuffer(
	_In_	NETADAPTER							Adapter,
	_In_	NET_FRAGMENT_RETURN_CONTEXT_HANDLE	RxReturnContext
)
{
	UNREFERENCED_PARAMETER(Adapter);

	RxReturnContext->IndicatedPackets--;

	// Clean up the lookaside buffer if this is the last packet
	if(RxReturnContext->IndicatedPackets == 0)
	{
		WdfObjectDelete(RxReturnContext->LookasideBufferMemory);
	}
}
```

## -see-also

[**NET_ADAPTER_RX_CAPABILITIES**](ns-netadapter-_net_adapter_rx_capabilities.md)
