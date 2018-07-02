---
UID: NF:netreceivescaling.NetAdapterSetReceiveScalingCapabilities
title: NetAdapterSetReceiveScalingCapabilities function
author: windows-driver-content
description: The NetAdapterSetReceiveScalingCapabilities method sets a net adapter's receive side scaling (RSS) capabilities.
ms.assetid: facda650-4f68-40e4-bfe0-f9b7adae4c7f
ms.author: windowsdriverdev
ms.date: 03/08/2018
ms.topic: function
ms.keywords: NetAdapterSetReceiveScalingCapabilities
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
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NetAdapterSetReceiveScalingCapabilities
product: Windows
targetos: Windows

---

# NetAdapterSetReceiveScalingCapabilities function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NetAdapterSetReceiveScalingCapabilities** method sets a net adapter's receive side scaling (RSS) capabilities.

## -parameters

### -param Adapter
The **NETADAPTER** object the driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities
A pointer to a driver-allocated and initialized [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure.

## -returns
This method does not return a value.

## -remarks
The client driver must call this method from its *[EVT_NET_ADAPTER_SET_CAPABILITIES](../netadapter/nc-netadapter-evt_net_adapter_set_capabilities.md)* event callback routine.



## -see-also
[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md)

[NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES_INIT](nf-netreceivescaling-net_adapter_receive_scaling_capabilities_init.md)

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)