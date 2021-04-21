---
UID: NE:ieee8021qtypes._NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
tech.root: netvista 
title: NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ieee8021qtypes.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ieee8021qtypes.h
api_name:
 - _NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
 - NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
f1_keywords:
 - _NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
 - ieee8021qtypes/_NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
 - NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
 - ieee8021qtypes/NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS
dev_langs:
 - c++
---

## -description

NetAdapterCx sets the **NET_PACKET_TX_IEEE8021Q_ACTION_FLAGS** enum to specify the IEEE 802.1 priority tagging and virtual LAN (VLAN) tagging capabilities that the client driver supports.

## -enum-fields

### -field NetPacketTxIeee8021qActionFlagPriorityRequired

### -field NetPacketTxIeee8021qActionFlagVlanRequired

## -remarks

If only IEEE 802.1 priority tagging is supported, NetAdapterCx sets this value to 1.
If only VLAN tagging is supported, NetAdapterCx sets this value to 2.
If both are supported, NetAdapterCx sets this value to 3.

## -see-also

[**NET_ADAPTER_OFFLOAD_IEEE8021Q_TAG_CAPABILITIES**](../netadapteroffload/ns-netadapteroffload-net_adapter_offload_ieee8021q_tag_capabilities.md)
