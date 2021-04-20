---
UID: NF:netadapteroffload.NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT
tech.root: netvista
title: NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT initializes a NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES structure.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapteroffload.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapteroffload.h
api_name:
 - NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT
f1_keywords:
 - NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT
 - netadapteroffload/NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md) structure.

## -parameters

### -param Ieee8021qCapabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md) structure.

### -param Flags

[_In_] Flags specifying whether the NIC can perform IEEE 802.1 priority and VLAN tagging.

## -remarks

The client driver calls **NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES** structure as a parameter to the [**NetAdapterOffloadSetIeee8021qTagCapabilities**](nf-netadapteroffload-netadapteroffloadsetieee8021qtagcapabilities.md) function to register it.

## -see-also

[**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md)

[**NetAdapterOffloadSetIeee8021qTagCapabilities**](nf-netadapteroffload-netadapteroffloadsetieee8021qtagcapabilities.md)

