---
UID: NF:netadapter.NetReceiveFilterGetPacketFilter
tech.root: netvista
title: NetReceiveFilterGetPacketFilter
ms.date: 04/15/2021
targetos: Windows
description: NetReceiveFilterGetPacketFilter retrieves the NET_PACKET_FILTER_FLAGS which describe the packet filters the network adapter supports.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
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
 - netadapter.h
api_name:
 - NetReceiveFilterGetPacketFilter
f1_keywords:
 - NetReceiveFilterGetPacketFilter
 - netadapter/NetReceiveFilterGetPacketFilter
dev_langs:
 - c++
---

## -description

The **NetReceiveFilterGetPacketFilter** function retrieves the **NET_PACKET_FILTER_FLAGS**. These flags describe the packet filters that the network adapter supports.

## -parameters

### -param ReceiveFilter

[_In_] A handle to a NETRECEIVEFILTER object.

## -returns

Returns a [**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md) enumeration.

## -remarks

Client drivers typically call **NetReceiveFilterGetPacketFilter** during their [*EvtNetAdapterSetReceiveFilter*](nc-netadapter-evt_net_adapter_set_receive_filter.md) callback to get an updated set of [**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md) that the NIC must filter.

## -see-also

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md) 

[**NetReceiveFilterGetMulticastAddressCount**](nf-netadapter-netreceivefiltergetmulticastaddresscount.md)

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)