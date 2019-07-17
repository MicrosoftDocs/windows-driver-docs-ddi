---
UID: NE:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE
title: _NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE enumeration specifies the type of receive side scaling (RSS) hash function that a NIC should use to compute the hash values for incoming packets.
tech.root: netvista
ms.assetid: fea3f37f-acd1-4af3-8e20-4473fc289430
ms.date: 03/06/2018
ms.topic: enum
f1_keywords:
 - "netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE"
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE, NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE, 
req.header: netreceivescaling.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netreceivescaling.h
api_name: 
- _NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE
product:
- Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE enumeration

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE** enumeration specifies the type of receive side scaling (RSS) hash function that a NIC should use to compute the hash values for incoming packets.

## -enum-fields

### -field NetAdapterReceiveScalingHashTypeNone : 
Unused for RSS-capable NIC client drivers.

### -field NetAdapterReceiveScalingHashTypeToeplitz : 
Indicates support for the Toeplitz hashing function.

## -remarks
Currently, **NetAdapterReceiveScalingHashTypeToeplitz** is the only hashing function available to NIC client drivers.



## -see-also

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
