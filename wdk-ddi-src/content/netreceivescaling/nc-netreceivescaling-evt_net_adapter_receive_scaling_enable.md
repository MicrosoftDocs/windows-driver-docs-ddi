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
> NetAdapterCx is preview only in Windows 10, version 1803.

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

### -param Adapter: 
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns
Returns STATUS_SUCCESS if RSS was successfully enabled. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks
Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** from their *[EvtNetAdapterSetCapabilities](../netadapter/nc-netadapter-evt_net_adapter_set_capabilities.md)* callback function.

The minimum NetAdapterCx version for *EvtNetAdapterReceiveScalingEnable* is 1.2.

### Example

configure things you need for RSS and turn it on. Need info like protocl types, hash type, secret key, then set the bit to turn it on.

Say that you shouldn't clear your indirection table or reset your indirection table from your enable callback. The framework will set your initial indirection table state. Also in disable.

## -see-also
[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling)