---
UID: NS:netadapter._NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
tech.root: netvista
title: NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: The NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES structure specifies a NIC's receive filtering capabilities.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
 - NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
f1_keywords:
 - _NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
 - netadapter/_NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
 - NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
 - netadapter/NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES** structure specifies a network interface card (NIC)'s receive filtering capabilities.

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field SupportedPacketFilters

A [**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md) enumeration. These flags describe the receive packet filters that the network adapter supports.

### -field MaximumMulticastAddresses

The maximum number of addresses that the multicast address list can contain.

### -field EvtSetReceiveFilter

A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md) callback function.

## -remarks

Call [**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT**](nf-netadapter-net_adapter_receive_filter_capabilities_init.md) to initialize this structure. The driver passes the initialized **NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES** structure as a parameter to [**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md) to register it.

## -see-also

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

[**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT**](nf-netadapter-net_adapter_receive_filter_capabilities_init.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md)

[**NetReceiveFilterGetPacketFilter**](nf-netadapter-netreceivefiltergetpacketfilter.md)

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)

[**NetReceiveFilterGetMulticastAddressCount**](nf-netadapter-netreceivefiltergetmulticastaddresscount.md)