---
UID: NC:netadapter.EVT_NET_ADAPTER_SET_RECEIVE_FILTER
tech.root: netvista
title: EVT_NET_ADAPTER_SET_RECEIVE_FILTER
ms.date: 04/15/2021
targetos: Windows
description: The client driver implements EvtNetAdapterSetReceiveFilter to set changes in a network adapter's active receive filtering capabilities.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: PASSIVE_LEVEL
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
 - LibDef
api_location:
 - netadapter.h
api_name:
 - EVT_NET_ADAPTER_SET_RECEIVE_FILTER
f1_keywords:
 - EVT_NET_ADAPTER_SET_RECEIVE_FILTER
 - netadapter/EVT_NET_ADAPTER_SET_RECEIVE_FILTER
dev_langs:
 - c++
---

## -description

The client driver implements the *EvtNetAdapterSetReceiveFilter* callback function to set changes in a network adapter's active receive filtering capabilities.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param unnamedParam2

[_In_] A handle to a NETRECEIVEFILTER object.

## -remarks

Register your implementation of this callback function by setting the appropriate parameter when calling [**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md).

## -see-also

[**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md)

[**NetReceiveFilterGetPacketFilter**](nf-netadapter-netreceivefiltergetpacketfilter.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT**](nf-netadapter-net_adapter_receive_filter_capabilities_init.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md)

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)

[**NetReceiveFilterGetMulticastAddressCount**](nf-netadapter-netreceivefiltergetmulticastaddresscount.md)


