---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
author: windows-driver-content
description: The NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration specifies how a net adapter handles unhashed receive side scaling (RSS) frames.
tech.root: netvista
ms.assetid: fed6bfa6-1388-490f-a586-33ee7590cb5f
ms.date: 07/13/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE, NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE, 
req.header: netreceivescaling.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE enumeration

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_RECEIVE_SCALING_UNHASHED_TARGET_TYPE** enumeration specifies how a net adapter handles unhashed receive side scaling (RSS) frames.

## -enum-fields

### -field NetAdapterReceiveScalingUnhashedTargetTypeUnspecified : 
Indicates that the device does not distribute unhashed frames to a specific hash index.

### -field NetAdapterReceiveScalingUnhashedTargetTypeHashIndex : 
Indicates that unhashed frames are delivered to the queue at the specified hash index. This requires the caller to specify the **UnhashedTargetIndex** member of the [**NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES**](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure with the hash index if the hash index is non-zero.

## -remarks

## -see-also

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
