---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY
title: _NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY
author: windows-driver-content
description: The NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY structure contains secret key data to verify RSS hash calculations.
ms.assetid: c00bfa60-8d5a-41e1-bc04-bdbad9d3ddc2
ms.author: windowsdriverdev
ms.date: 03/06/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY, *PNET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY, NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY, 
req.header: netreceivescaling.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY, *PNET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY
product: Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY structure contains secret key data to verify RSS hash calculations.

## -struct-fields

### -field Count
The size, in bytes, of the secret key.

### -field Key
The secret key. This member is 40 bytes (320 bits) for the **NetAdapterReceiveScalingHashTypeToeplitz** hash function.

## -remarks
NetAdapterCx provides the secret key to NIC client drivers when it invokes the *[EvtNetAdapterReceiveScalingSetHashSecretKey](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_hash_secret_key.md)* callback function. The NIC then uses this secret key to verify its calculations for the RSS hash function.



## -see-also

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)

[NET_ADAPTER_RECEIVE_SCALING_HASH_TYPE](ne-netreceivescaling-_net_adapter_receive_scaling_hash_type.md)