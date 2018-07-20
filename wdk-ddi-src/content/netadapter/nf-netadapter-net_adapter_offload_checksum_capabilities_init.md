---
UID: NF:netadapter.NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
title: NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT function
author: windows-driver-content
description: The NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT method initializes a NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES structure.
ms.assetid: 22fa6f17-30aa-4ca4-ab53-a3c95591a68f
ms.author: windowsdriverdev
ms.date: 07/19/2018
ms.topic: function
ms.keywords: NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib:
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
-	NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT
product: Windows
targetos: Windows


---

# NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure.

## -parameters

### -param ChecksumCapabilities

A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure.

### -param IPv4

A flag specifying whether the hardware can calculate and validate IPv4 checksum.

### -param Tcp

A flag specifying whether the hardware can calculate and validate TCP checksum.

### -param Udp

A flag specifying whether the hardware can calculate and validate UDP checksum.

## -returns

This method does not return a value.

## -remarks

Client drivers typically call this method from within their [*EVT_NET_ADAPTER_SET_CAPABILITIES*](nc-netadapter-evt_net_adapter_set_capabilities.md) callback function when configuring hardware checksum offload capabilities. The [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md) structure initialized by this method is passed as a parameter to the [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md) method.

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES**](ns-netadapter-_net_adapter_offload_checksum_capabilities.md)

[*EVT_NET_ADAPTER_SET_CAPABILITIES*](nc-netadapter-evt_net_adapter_set_capabilities.md)