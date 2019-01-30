---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY (netreceivescaling.h)
description: The EvtNetAdapterReceiveScalingSetHashSecretKey callback function is implemented by the client driver to set the hash secret key for the network interface controller (NIC).
tech.root: netvista
ms.assetid: 9144fad7-c6d6-4d67-9ad7-45e9a0cf31f6
ms.date: 03/12/2018
ms.topic: callback
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
-	EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
product:
-	Windows
targetos: Windows
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY callback function

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The *EvtNetAdapterReceiveScalingSetHashSecretKey* callback function is implemented by the client driver to set the hash secret key for the network interface controller (NIC).

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY EvtNetAdapterReceiveScalingSetHashSecretKey; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetHashSecretKey 
(
	_In_	NETADAPTER 										Adapter,
	_In_	PCNET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY	HashSecretKey
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY;
```

## -parameters

### -param Adapter 
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HashSecretKey: 
A pointer to a [NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md) structure that contains the hash secret key for validating hash calculations.

## -returns
Returns STATUS_SUCCESS if the hash secret key was set successfully. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks
Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).



### Example

In this callback, NIC client drivers program the supplied hash secret key to their hardware for use in verifying RSS hash calculations.

```C++
NTSTATUS
MyEvtNetAdapterReceiveScalingSetHashSecretKey(
	_In_	NETADAPTER 										Adapter,
	_In_	PCNET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY	HashSecretKey	
)
{
	const UINT32* key = (const UINT32*)HashSecretKey->Key;
	if(!MyHardwareRssSetHashSecretKey)
	{
		WdfDeviceSetFailed(Adapter->WdfDevice, WdfDeviceFailedAttemptRestart);
		return STATUS_UNSUCCESSFUL;
	}

	return STATUS_SUCCESS;
}
```

## -see-also
[NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
