---
UID: NF:netadapter.NetReceiveFilterGetMulticastAddressList
tech.root: netvista
title: NetReceiveFilterGetMulticastAddressList
ms.date: 04/15/2021
targetos: Windows
description: NetReceiveFilterGetMulticastAddressList retrieves the list of addresses that can receive multicast packets.
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
 - NetReceiveFilterGetMulticastAddressList
f1_keywords:
 - NetReceiveFilterGetMulticastAddressList
 - netadapter/NetReceiveFilterGetMulticastAddressList
dev_langs:
 - c++
---

## -description

The **NetReceiveFilterGetMulticastAddressList** function retrieves a network adapter's multicast address list.

## -parameters

### -param ReceiveFilter

[_In_] A handle to a NETRECEIVEFILTER object.

## -returns

Returns a pointer to the first **NET_ADAPTER_LINK_LAYER_ADDRESS** structure in the network adapter's multicast address list.

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterSetReceiveFilter*](nc-netadapter-evt_net_adapter_set_receive_filter.md) callback to get an updated multicast address list that the NIC must enable.

## -see-also

[**NetReceiveFilterGetMulticastAddressCount**](nf-netadapter-netreceivefiltergetmulticastaddresscount.md)

[**NetReceiveFilterGetPacketFilter**](nf-netadapter-netreceivefiltergetpacketfilter.md)

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)


