---
UID: NS:netreceivescaling._NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
title: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
author: windows-driver-content
description: The NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure represents a single entry in the receive side scaling (RSS) indirection table.
ms.assetid: 053929b4-7420-40ac-a844-df62e055607b
ms.author: windowsdriverdev
ms.date: 03/07/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY, NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY, 
req.header: netreceivescaling.h
req.include-header:
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netreceivescaling.h
apiname: 
-	_NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY
product:
-	Windows
targetos: Windows
---

# _NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY structure

## -description
> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

The **NET_ADAPTER_RECEIVE_SCALING_INDIRECTION_ENTRY** structure represents a move operation for a single entry in the receive side scaling (RSS) indirection table. 

## -struct-fields

### -field Queue
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

[NetAdapterCx Receive Side Scaling](https://docs.microsoft.com/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)