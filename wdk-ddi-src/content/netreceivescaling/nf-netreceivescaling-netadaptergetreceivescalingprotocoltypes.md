---
UID: NF:netreceivescaling.NetAdapterGetReceiveScalingProtocolTypes
title: NetAdapterGetReceiveScalingProtocolTypes function
author: windows-driver-content
description: The **NetAdapterGetReceiveScalingProtocolTypes** method gets the receive side scaling (RSS) protocol types to use in hash calculations for a net adapter.
ms.assetid: 77e37296-c9bf-4576-8dc9-0d4e9989980e
ms.author: windowsdriverdev
ms.date: 03/08/2018
ms.topic: function
ms.keywords: NetAdapterGetReceiveScalingProtocolTypes
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
-	NetAdapterGetReceiveScalingProtocolTypes
product: Windows
targetos: Windows

---

# NetAdapterGetReceiveScalingProtocolTypes function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetAdapterGetReceiveScalingProtocolTypes** method gets the receive side scaling (RSS) protocol types to use in hash calculations for a net adapter.

## -parameters

### -param Adapter
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns
Returns a [NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_protocol_type.md) enumeration value that indicates the protocol types for calculating hash values.

## -remarks
Client drivers typically call this method from their *[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)* callback function when enabling RSS on the NIC.

The minimum NetAdapterCx version for **NetAdapterGetReceiveScalingProtocolTypes** is 1.2.

## -see-also
*[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)*

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)