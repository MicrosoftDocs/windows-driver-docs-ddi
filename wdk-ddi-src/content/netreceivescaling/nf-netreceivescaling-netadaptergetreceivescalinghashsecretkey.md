---
UID: NF:netreceivescaling.NetAdapterGetReceiveScalingHashSecretKey
title: NetAdapterGetReceiveScalingHashSecretKey function
author: windows-driver-content
description: The NetAdapterGetReceiveScalingHashSecretKey method gets the receive side scaling (RSS) hash secret key for a net adapter.
ms.assetid: bb77af9c-8feb-4e75-afb8-3816a2fc9240
ms.author: windowsdriverdev
ms.date: 03/06/2018
ms.topic: function
ms.keywords: NetAdapterGetReceiveScalingHashSecretKey
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
-	NetAdapterGetReceiveScalingHashSecretKey
product:
-	Windows
targetos: Windows

---

# NetAdapterGetReceiveScalingHashSecretKey function


## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NetAdapterGetReceiveScalingHashSecretKey** method gets the receive side scaling (RSS) hash secret key for a net adapter.

## -parameters

### -param Adapter
The **NETADAPTER** object the client driver obtained in a previous call to [NetAdapterCreate](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns
Returns a pointer to a [NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md) structure that contains the hash secret key.

## -remarks
Client drivers typically call this method from their *[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)* callback function when enabling RSS on the NIC.



## -see-also
*[EvtNetAdapterReceiveScalingEnable](nc-netreceivescaling-evt_net_adapter_receive_scaling_enable.md)*

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)