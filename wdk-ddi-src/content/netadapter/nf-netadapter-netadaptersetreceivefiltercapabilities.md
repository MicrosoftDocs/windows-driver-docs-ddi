---
UID: NF:netadapter.NetAdapterSetReceiveFilterCapabilities
tech.root: netvista
title: NetAdapterSetReceiveFilterCapabilities
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NetAdapterSetReceiveFilterCapabilities sets the receive filtering capabilities of a net adapter.
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
 - NetAdapterSetReceiveFilterCapabilities
f1_keywords:
 - NetAdapterSetReceiveFilterCapabilities
 - netadapter/NetAdapterSetReceiveFilterCapabilities
dev_langs:
 - c++
---

## -description

The **NetAdapterSetReceiveFilterCapabilities** function sets the receive filtering capabilities of a net adapter.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param Capabilities

[_In_] A pointer to a driver-allocated and initialized [**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md) structure that describes the net adapter's receive filtering capabilities.

## -remarks

Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

## -see-also

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md)

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT**](nf-netadapter-net_adapter_receive_filter_capabilities_init.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md)

[**NetReceiveFilterGetMulticastAddressList**](nf-netadapter-netreceivefiltergetmulticastaddresslist.md)

[**NetReceiveFilterGetMulticastAddressCount**](nf-netadapter-netreceivefiltergetmulticastaddresscount.md)