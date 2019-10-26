---
UID: NF:netadapter.NET_ADAPTER_WAKE_REASON_PACKET_INIT
title: NET_ADAPTER_WAKE_REASON_PACKET_INIT function (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_WAKE_REASON_PACKET_INIT method initializes a NET_ADAPTER_WAKE_REASON_PACKET structure.
tech.root: netvista
ms.assetid: 3ef00ff3-cb05-4461-8656-d56aca530b9e
ms.author: windowsdriverdev
ms.date: 10/25/2019
ms.topic: function
f1_keywords:
 - "netadapter/NET_ADAPTER_WAKE_REASON_PACKET_INIT"
ms.keywords: NET_ADAPTER_WAKE_REASON_PACKET_INIT
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level as long as target memory is resident
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- netadapter.h
api_name: 
- NET_ADAPTER_WAKE_REASON_PACKET_INIT
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_WAKE_REASON_PACKET_INIT function


## -description

The **NET_ADAPTER_WAKE_REASON_PACKET_INIT** method initializes a [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure.

## -parameters

### -param Reason

A pointer to a driver allocated [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure.

## -returns

This method does not return a value.

## -remarks

This method zeroes out the memory for the **NET_ADAPTER_WAKE_REASON_PACKET** structure, then sets the **Size** member.

## -see-also