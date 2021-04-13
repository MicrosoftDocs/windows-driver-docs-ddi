---
UID: NF:netadapter.NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT
tech.root: netvista
title: NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: The NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT function initializes a NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES structure. 
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
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT
f1_keywords:
 - NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT
 - netadapter/NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md) structure. 

## -parameters

### -param Capabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md) structure.

### -param EvtSetReceiveFilter

[_In_] A pointer to the client driver's implementation of the [*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md) callback function.

## -remarks

The client driver calls **NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES** structure as a parameter to the [**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md) function to register it.

## -see-also

[*EVT_NET_ADAPTER_SET_RECEIVE_FILTER*](nc-netadapter-evt_net_adapter_set_receive_filter.md)

[**NET_ADAPTER_RECEIVE_FILTER_CAPABILITIES**](ns-netadapter-net_adapter_receive_filter_capabilities.md)

[**NetAdapterSetReceiveFilterCapabilities**](nf-netadapter-netadaptersetreceivefiltercapabilities.md)

[**NET_PACKET_FILTER_FLAGS**](ne-netadapter-net_packet_filter_flags.md)
