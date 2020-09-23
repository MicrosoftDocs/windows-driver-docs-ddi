---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
title: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure represents a series of move operations for all entries in the receive side scaling (RSS) indirection table.
tech.root: netvista
ms.assetid: 62dc57e0-7c2d-415a-8ab9-3fc973b5be87
ms.date: 07/13/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure"]
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, *PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES,
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, *PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
targetos: Windows
f1_keywords:
 - _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
 - netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
 - NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netreceivescaling.h
api_name:
 - _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
---

# _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure


## -description

The **NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES** structure represents a series of move operations for all entries in the receive side scaling (RSS) indirection table.

## -struct-fields

### -field Entries

An array of [**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md) structures, each representing a move for an entry in the indirection table.

### -field Length

The length, in bytes, of **Entries**.

## -remarks

NetAdapterCx passes a pointer to this structure as input to a NIC client driver's *[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)* event callback function.

## -see-also

*[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)*

[**NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY**](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entry.md)

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)