---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
title: EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
author: windows-driver-content
description: The EvtNetAdapterReceiveScalingEnable callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC).
ms.assetid: a37af139-8c98-4733-b2d2-cb0c9d67de35
ms.author: windowsdriverdev
ms.date: 03/08/2018
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
-	EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE
product: Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE callback function

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtNetAdapterReceiveScalingEnable* callback function is implemented by the client driver to enable receive side scaling (RSS) for a network interface controller (NIC).

## -prototype

```
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE EvtNetAdapterReceiveScalingEnable; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingEnable 
(
	_In_ NETADAPTER Adapter
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_ENABLE *PFN_NET_ADAPTER_RECEIVE_SCALING_ENABLE;
```

## -parameters

### -param Adapter 
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns
Returns STATUS_SUCCESS if RSS was successfully enabled. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks
Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** from their *[EvtNetAdapterSetCapabilities](../netadapter/nc-netadapter-evt_net_adapter_set_capabilities.md)* callback function.



### Example
In this callback, NIC client drivers get what information they need to turn RSS on for their NIC, such as the protocol types, hash function type, and hash secret key. Clients can use any of these helper methods to get the information they need:

- [NetAdapterGetReceiveScalingProtocoltypes](nf-netreceivescaling-netadaptergetreceivescalingprotocoltypes.md)
- [NetAdapterGetReceiveScalingHashType](nf-netreceivescaling-netadaptergetreceivescalinghashtype.md)
- [NetAdapterGetReceiveScalingHashSecretKey](nf-netreceivescaling-netadaptergetreceivescalinghashsecretkey.md)

Then, clients turn RSS on with the supplied information by setting the appropriate control bits in hardware. In this example, the client gets protocol types before enabling RSS.

> [!IMPORTANT]
> Client drivers should **not** clear or reset their indirection table from their *EvtNetAdapterReceiveScalingEnable* callback. The framework will set the driver's initial indirection table state.

```C++
NTSTATUS
MyEvtNetAdapterReceiveScalingEnable(
	_In_ NETADAPTER Adapter
)
{
	NTSTATUS status = STATUS_SUCCESS;

	const NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE protocolTypes = NetAdapterGetReceiveScalingProtocolTypes(Adapter);

	UINT32 controlBitsEnable = MY_RSS_MULTI_CPU_ENABLE | MY_RSS_HASH_BITS_ENABLE;

	// Set the appropriate control bits

	if(protocolTypes & NetAdapterReceiveScalingProtocolTypeIPv4)
	{
		controlBitsEnable |= MY_RSS_IPV4_ENABLE;

		if (protocolTypes & NetAdapterReceiveScalingProtocolTypeTcp)
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
[NetAdapterGetReceiveScalingProtocoltypes](nf-netreceivescaling-netadaptergetreceivescalingprotocoltypes.md)

[NetAdapterGetReceiveScalingHashType](nf-netreceivescaling-netadaptergetreceivescalinghashtype.md)

[NetAdapterGetReceiveScalingHashSecretKey](nf-netreceivescaling-netadaptergetreceivescalinghashsecretkey.md)

*[EvtNetAdapterReceiveScalingDisable](nc-netreceivescaling-evt_net_adapter_receive_scaling_disable.md)*

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)