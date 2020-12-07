---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration specifies how a net adapter handles unhashed receive side scaling (RSS) frames.
tech.root: netvista
ms.date: 07/13/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration"]
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE, NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE,
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
targetos: Windows
f1_keywords:
 - _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
 - netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
 - NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netreceivescaling.h
api_name:
 - _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
---

# _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration


## -description

The **NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE** enumeration specifies how a net adapter handles unhashed receive side scaling (RSS) frames.

## -enum-fields

### -field NetAdapterReceiveScalingUnhashedTargetTypeUnspecified : 

Indicates that the device does not distribute unhashed frames to a specific hash index.

### -field NetAdapterReceiveScalingUnhashedTargetTypeHashIndex : 

Indicates that unhashed frames are delivered to the queue at the specified hash index. This requires the caller to specify the **UnhashedTargetIndex** member of the [**NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES**](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure with the hash index if the hash index is non-zero.

## -remarks

## -see-also

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
