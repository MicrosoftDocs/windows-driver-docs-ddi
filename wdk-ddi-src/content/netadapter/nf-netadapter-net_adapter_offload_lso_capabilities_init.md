---
UID: NF:netadapter.NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT function (netadapter.h)
description: The NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT method initializes a NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES structure.
tech.root: netvista
ms.assetid: cc94cd92-487e-4a09-9852-e1c9a3315088
ms.date: 07/20/2018
ms.topic: function
ms.keywords: NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	netadaptercxstub.lib
api_name: 
-	NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md) structure.

## -parameters

### -param LsoCapabilities

A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md) structure.

### -param IPv4

A flag specifying whether the NIC can segment a large TCP packet on IPv4.

### -param IPv6

A flag specifying whether the NIC can segment a large TCP packet on IPv6.

### -param MaximumOffloadSize

The maximum bytes of user data that the transport can pass to the NIC driver in a single packet.

### -param MinimumSegmentCount

The minimum number of segments by which a large TCP packet must be divisible before the transport can offload it to the hardware for segmentation.

## -returns

This method does not return a value.

## -remarks

The [**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md) structure initialized by this method is passed as a parameter to the [**NetAdapterOffloadSetLsoCapabilities**](nf-netadapter-netadapteroffloadsetlsocapabilities.md) method.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_LSO_CAPABILITIES**](ns-netadapter-_net_adapter_offload_lso_capabilities.md)

[**NetAdapterOffloadSetLsoCapabilities**](nf-netadapter-netadapteroffloadsetlsocapabilities.md)
