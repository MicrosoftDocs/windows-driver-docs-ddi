---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
title: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure represents a single entry in the receive side scaling (RSS) indirection table.
tech.root: netvista
ms.date: 03/07/2018
keywords: ["NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure"]
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY, NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY,
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
targetos: Windows
f1_keywords:
 - _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
 - netreceivescaling/_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
 - NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
 - netreceivescaling/NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
topictype:
 - apiref
apitype:
 - HeaderDef
apilocation:
 - netreceivescaling.h
apiname:
 - _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
---

# _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure


## -description

The **NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY** structure represents a move operation for a single entry in the receive side scaling (RSS) indirection table.

## -struct-fields

### -field PacketQueue

The new receive queue for the entry.

### -field Status

An NTSTATUS value that indicates the status of the move operation for this entry.

### -field Index

The hash index in the indirection table for this entry.

## -remarks

Each **NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY** structure is contained within a [NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md) structure.

## -see-also

*[EvtNetAdapterReceiveScalingSetIndirectionEntries](nc-netreceivescaling-evt_net_adapter_receive_scaling_set_indirection_entries.md)*

[NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES](ns-netreceivescaling-_net_adapter_receive_scaling_indirection_entries.md)

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
