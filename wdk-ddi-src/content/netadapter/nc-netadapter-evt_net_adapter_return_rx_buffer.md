---
UID: NC:netadapter.EVT_NET_ADAPTER_RETURN_RX_BUFFER
title: EVT_NET_ADAPTER_RETURN_RX_BUFFER
author: windows-driver-content
description: Implement this optional callback function to perform cleanup on a receive buffer for which you previously specified manual fragment allocation and attachment.
ms.assetid: E999C47A-CAE1-42AB-9900-4118EFFAEE0D
ms.author: windowsdriverdev
ms.date: 02/15/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	netadapter.h
apiname: 
-	EVT_NET_ADAPTER_RETURN_RX_BUFFER
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RETURN_RX_BUFFER callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Implement this optional callback function to perform cleanup on a [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffer for which you previously specified manual fragment allocation and attachment.

## -prototype

```c++
//Declaration

EVT_NET_ADAPTER_RETURN_RX_BUFFER EvtNetAdapterReturnRxBuffer; 

// Definition

VOID EvtNetAdapterReturnRxBuffer 
(
	_In_	NETADAPTER	Adapter,
	_In_	PVOID		RxBufferVirtualAddress,
	_In_	PVOID		RxBufferReturnContext
)
{...}

typedef EVT_NET_ADAPTER_RETURN_RX_BUFFER *PFN_NET_ADAPTER_RETURN_RX_BUFFER;
```

## -parameters

### -param Adapter 
The network adapter object that the client created in a prior call to [NetAdapterCreate](nf-netadapter-netadaptercreate.md).

### -param RxBufferVirtualAddress 
A pointer to the virtual address of the [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive buffer. Cast this member to a **PNET_PACKET_FRAGMENT** to retrieve the fragment.

### -param RxBufferReturnContext 
A pointer to a driver-allocated context space structure.

## -returns
This callback function does not return a value.

## -remarks
Register your implementation of this callback function by setting the appropriate member of [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure and then calling [NetAdapterSetDatapathCapabilities](nf-netadapter-netadaptersetdatapathcapabilities.md) during *[EVT_NET_ADAPTER_SET_CAPABILITIES](nc-netadapter-evt_net_adapter_set_capabilities.md)*.

This callback function is optional unless the net adapter client driver initializes its [NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md) structure using the [NET_ADAPTER_RX_CAPABILITIES_INIT_DRIVER_MANAGED](nf-netadapter-net_adapter_rx_capabilities_init_driver_managed.md) method. By using this initialization method, the driver tells the operating system that it is managing allocation and attachment of [NET_PACKET_FRAGMENT](../netpacket/ns-netpacket-_net_packet_fragment.md) receive bufffers manually, so it must provide this callback function in this case for the operating system to invoke once the system is finished with the buffer.

### Example
In this callback function, the client driver can perform whatever cleanup or follow-up actions it needs now that the operating system has finished with this receive buffer. In the following example, the return context contains a member to track the number of indicated packets, as well as a memory object used for a lookaside buffer during receive processing. Error handling has been left out for clarity.

```c++
VOID
MyReturnRxBuffer(
	_In_	NETADAPTER	Adapter,
	_In_	PVOID		RxBufferVirtualAddress,
	_In_	PVOID		RxBufferReturnContext
)
{
	UNREFERENCED_PARAMETER(Adapter);
	UNREFERENCED_PARAMETER(RxBufferVirtualAddress);

	// Get the context
	PMY_RX_BUFFER_RETURN_CONTEXT context = (PMY_RX_BUFFER_RETURN_CONTEXT)RxBufferReturnContext;
	
	context->IndicatedPackets--;

	// Clean up the lookaside buffer if this is the last packet
	if(context->IndicatedPackets == 0)
	{
		WdfObjectDelete(context->LookasideBufferMemory);
	}
}
```

## -see-also

[NET_ADAPTER_RX_CAPABILITIES](ns-netadapter-_net_adapter_rx_capabilities.md)