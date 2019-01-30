---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
title: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES (netreceivescaling.h)
description: The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure represents a series of move operations for all entries in the receive side scaling (RSS) indirection table. 
tech.root: netvista
ms.assetid: 62dc57e0-7c2d-415a-8ab9-3fc973b5be87
ms.date: 07/13/2018
ms.topic: struct
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, *PNET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES, 
req.header: netreceivescaling.h
req.include-header:
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRIES structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

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

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
