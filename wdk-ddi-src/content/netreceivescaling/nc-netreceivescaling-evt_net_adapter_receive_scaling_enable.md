---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
title: EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE (netreceivescaling.h)
description: The EvtNetAdapterReceiveScalingEnable callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC).
tech.root: netvista
ms.date: 07/13/2018
keywords: ["EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE callback function"]
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
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
targetos: Windows
f1_keywords:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
 - netreceivescaling/EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netreceivescaling.h
api_name:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE callback function


## -description

The *EvtNetAdapterReceiveScalingEnable* callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC).

## -parameters

### -param Adapter 

The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HashType

A [**NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE**](ne-netreceivescaling-_net_adapter_receive_scaling_hash_type.md) value that specifies the type of receive side scaling (RSS) hash function that a NIC should use to compute the hash values for incoming packets.

### -param ProtocolType

A [**NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE**](ne-netreceivescaling-_net_adapter_receive_scaling_protocol_type.md) value that specifies the portion of received network data that an RSS-capable NIC must use to calculate an RSS hash value.

## -returns

Returns STATUS_SUCCESS if RSS was successfully enabled. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE EvtNetAdapterReceiveScalingEnable; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingEnable 
(
	_In_ NETADAPTER Adapter,
	_In_ NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE HashType,
	_In_ NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE ProtocolType
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE *PFN_NET_ADAPTER_RECEIVE_SCALING_ENABLE;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

### Example

In this callback, clients turn RSS on with the supplied information by setting the appropriate control bits in hardware.

> [!IMPORTANT]
> Client drivers should **not** clear or reset their indirection table from their *EvtNetAdapterReceiveScalingEnable* callback. The framework will set the driver's initial indirection table state.

```C++
NTSTATUS
MyEvtNetAdapterReceiveScalingEnable(
	_In_ NETADAPTER Adapter,
	_In_ NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE HashType,
	_In_ NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE ProtocolType
)
{
	NTSTATUS status = STATUS_SUCCESS;

	// Not using the hash type in this example
	UNREFERENCED_PARAMETER(HashType);

	UINT32 controlBitsEnable = MY_RSS_MULTI_CPU_ENABLE | MY_RSS_HASH_BITS_ENABLE;

	// Set the appropriate control bits for IPv4
	if(ProtocolType & NetAdapterReceiveScalingProtocolTypeIPv4)
	{
		controlBitsEnable |= MY_RSS_IPV4_ENABLE;

		if (ProtocolType & NetAdapterReceiveScalingProtocolTypeTcp)
        {
            controlBitsEnable |= MY_RSS_IPV4_TCP_ENABLE;
        }
	}

	// Repeat for IPv6
	...

	// Set the bits in hardware
	if(!MyHardwareRssSetControl(controlBitsEnable))
	{
		WdfDeviceSetFailed(Adapter->WdfDevice, WdfDeviceFailedAttemptRestart);
        return STATUS_UNSUCCESSFUL;
	}

	// Perform other tasks like restarting the Rx queue

	return STATUS_SUCCESS;
}
```

## -see-also

*[EvtNetAdapterReceiveScalingDisable](nc-netreceivescaling-evt_net_adapter_receive_scaling_disable.md)*

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
