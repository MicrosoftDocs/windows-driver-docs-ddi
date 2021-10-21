---
UID: NF:netadapter.NetReceiveFilterGetMulticastAddressCount
tech.root: netvista
title: NetReceiveFilterGetMulticastAddressCount
ms.date: 04/15/2021
targetos: Windows
description: NetReceiveFilterGetMulticastAddressCount retrieves the number of addresses in the multicast address list. 
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
 - NetReceiveFilterGetMulticastAddressCount
f1_keywords:
 - NetReceiveFilterGetMulticastAddressCount
 - netadapter/NetReceiveFilterGetMulticastAddressCount
dev_langs:
 - c++
---

## -description

The **NetReceiveFilterGetMulticastAddressCount** function retrieves the number of addresses in a network adapter's multicast address list. 

## -parameters

### -param ReceiveFilter [_In_]

A handle to a NETRECEIVEFILTER object.

## -returns

Returns the number of addresses in the multicast address list. 

## -remarks

Client drivers typically call this function during their [*EvtNetAdapterSetReceiveFilter*](nc-netadapter-evt_net_adapter_set_receive_filter.md) callback to get an updated count of multicast addresses.

## -see-also

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)

[**NetReceiveFilterGetPacketFilter**](nf-netadapter-netreceivefiltergetpacketfilter.md)

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

