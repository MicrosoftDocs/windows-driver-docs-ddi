---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
author: windows-driver-content
description: The NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration specifies the portion of received network data that a NIC must use to calculate an RSS hash value.
ms.assetid: 4a22dc5e-257b-411e-aae8-9abd92143bc5
ms.author: windowsdriverdev
ms.date: 03/07/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE, NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netreceivescaling.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE** enumeration specifies the portion of received network data that an RSS-capable NIC must use to calculate an RSS hash value.

## -enum-fields

### -field NetAdapterReceiveScalingProtocolTypeNone : 
Unused for RSS-capable NIC client drivers.

### -field NetAdapterReceiveScalingProtocolTypeIPv4 : 
Indicates that the hardware can calculate hashes for IPv4 packets.

### -field NetAdapterReceiveScalingProtocolTypeIPv4Options : 
Indicates that the hardware understands IPv4 options. This constant requires that **NetAdapterReceiveScalingProtocolTypeIPv4** is set.

### -field NetAdapterReceiveScalingProtocolTypeIPv6 : 
Indicates that the hardware can calculate hashes for IPv6 packets.

### -field NetAdapterReceiveScalingProtocolTypeIPv6Extensions : 
Indicates that the hardware understands IPv6 extension headers. This constant requires that **NetAdapterReceiveScalingProtocolTypeIPv6** is set.

### -field NetAdapterReceiveScalingProtocolTypeTcp : 
Indicates that the hardware supports 4-tuple TCP header hash calculation.

### -field NetAdapterReceiveScalingProtocolTypeUdp : 
Indicates that the hardware supports 4-tuple UDP header hash calculation.

## -remarks
The **ReceiveScalingProtocolTypes** member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure is a bitwise OR of **NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE** constants. NIC client drivers can OR multiple values together to indicate which protocol types they support for RSS.



## -see-also

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)