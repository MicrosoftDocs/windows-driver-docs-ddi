---
UID: NS:netadapteroffload._NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
tech.root: netvista
title: NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES describes a NIC's IEEE 802.1 priority and VLAN tagging capabilities.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: netadapteroffload.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - _NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
f1_keywords:
 - _NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
 - netadapteroffload/_NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
 - NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
 - netadapteroffload/NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES** structure describes a network interface card (NIC)'s IEEE 802.1 priority tagging and virtual LAN (VLAN) tagging capabilities.

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field Flags

Flags specifying whether the NIC can perform IEEE 802.1 priority and VLAN tagging.


| Flag | Description |
| --- | --- |
| NetAdapterOffloadIeee8021PriorityTaggingFlag | Set if the NIC is capable of performing IEEE 802.1 priority tagging. |
| NetAdapterOffloadIeee8021VlanTaggingFlag | Set if the NIC is capable of performing VLAN tagging. |

## -remarks

Call [**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities_init.md) to initialize this structure. The client driver passes an initialized **NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES** structure as a parameter to [**NetAdapterOffloadSetIeee8021qTagCapabilities**](nf-netadapteroffload-netadapteroffloadsetieee8021qtagcapabilities.md).

## -see-also

[**NET_ADAPTER_OFFLOAD_TX_CHECKSUM_CAPABILITIES_INIT**](nf-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities_init.md)

[**NetAdapterOffloadSetIeee8021qTagCapabilities**](nf-netadapteroffload-netadapteroffloadsetieee8021qtagcapabilities.md)