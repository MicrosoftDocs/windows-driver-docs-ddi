---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration specifies the portion of received network data that a NIC must use to calculate an RSS hash value.
tech.root: netvista
ms.date: 03/07/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration"]
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE, NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE,
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
targetos: Windows
f1_keywords:
 - _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
 - netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
 - NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netreceivescaling.h
api_name:
 - _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE
---

# _NET_ADAPTER_RECEIVE_SCALING_PROTOCOL_TYPE enumeration


## -description

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

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
