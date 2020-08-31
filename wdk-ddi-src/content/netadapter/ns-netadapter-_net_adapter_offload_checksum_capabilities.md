---
UID: NS:netadapter._NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
title: _NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES (netadapter.h)
description: The NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES structure describes a network interface card (NIC)'s capabilities for offloading checksum calculation and validation.
tech.root: netvista
ms.assetid: edf69542-3428-4919-ac04-872429a873d8
ms.date: 01/18/2019
keywords: ["NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES structure"]
ms.keywords: _NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES, NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES,
req.header: netadapter.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES, *PNET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
 - netadapter/_NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
 - netadapter/NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES
---

# _NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES structure


## -description

The **NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES** structure describes a network interface card (NIC)'s capabilities for offloading checksum calculation and validation.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field IPv4

A flag specifying whether the NIC can calculate and validate IPv4 checksum.

### -field Tcp

A flag specifying whether the NIC can calculate and validate TCP checksum.

### -field Udp

 
A flag specifying whether the NIC can calculate and validate UDP checksum.

### -field EvtAdapterOffloadSetChecksum

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_OFFLOAD_SET_CHECKSUM*](nc-netadapter-evt_net_adapter_offload_set_checksum.md) callback function.

## -remarks

Call [**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT**](nf-netadapter-net_adapter_offload_checksum_capabilities_init.md) to initialize this structure. An initialized **NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES** structure is passed as a parameter to [**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md).

## -see-also

[NetAdapterCx hardware offloads](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-hardware-offloads)

[**NET_ADAPTER_OFFLOAD_CHECKSUM_CAPABILITIES_INIT**](nf-netadapter-net_adapter_offload_checksum_capabilities_init.md)

[**NetAdapterOffloadSetChecksumCapabilities**](nf-netadapter-netadapteroffloadsetchecksumcapabilities.md)

