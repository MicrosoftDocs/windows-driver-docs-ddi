---
UID: NF:netadapter.NetReceiveFilterGetMulticastAddressCount
tech.root: netvista
title: NetReceiveFilterGetMulticastAddressCount
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NetReceiveFilterGetMulticastAddressList retrieves the number of addresses in the multicast address list. 
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
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
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

The **NetReceiveFilterGetMulticastAddressList** function retrieves the number of addresses in a net adapter's multicast address list. 

## -parameters

### -param ReceiveFilter

[_In_] A handle to a NETRECEIVEFILTER object.

## -returns

Returns the number of addresses in the multicast address list. 

## -remarks

## -see-also

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md)

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT**](nf-netadapter-net_adapter_receive_filter_capabilities_init.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md)

[**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md)
