---
UID: NE:netadapter._NET_ADAPTER_PAUSE_FUNCTIONS
title: _NET_ADAPTER_PAUSE_FUNCTIONS (netadapter.h)
description: Specifies a client driver's support for the IEEE 802.3 pause frames.
tech.root: netvista
ms.assetid: 758bf862-40d5-4035-8bd4-eaa4b4246d26
ms.date: 02/05/2018
ms.topic: enum
f1_keywords:
 - "netadapter/NET_ADAPTER_PAUSE_FUNCTIONS"
ms.keywords: _NET_ADAPTER_PAUSE_FUNCTIONS, NET_ADAPTER_PAUSE_FUNCTIONS, *PNET_ADAPTER_PAUSE_FUNCTIONS, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_PAUSE_FUNCTIONS, *PNET_ADAPTER_PAUSE_FUNCTIONS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netadapter.h
api_name: 
- NET_ADAPTER_PAUSE_FUNCTIONS
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_ADAPTER_PAUSE_FUNCTIONS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

Specifies a client driver's support for the IEEE 802.3 pause frames.

## -enum-fields

### -field NetAdapterPauseFunctionsUnsupported : 
Indicates that the adapter or link partner does not support pause frames.

### -field NetAdapterPauseFunctionsSendOnly : 
Indicates that the adapter and link partner only support sending pause frames from the adapter to the link partner.

### -field NetAdapterPauseFunctionsReceiveOnly : 
Indicates that the adapter and link partner only support sending pause frames from the link partner to the adapter.

### -field NetAdapterPauseFunctionsSendAndReceive : 
Indicates that the adapter and link partner support sending and receiving pause frames in both transint and receive directions.

### -field NetAdapterPauseFunctionsUnknown : 
Indicates that pause frame negotiation is in progress. The pause frame support that the link partner provides is unknown.

## -remarks

The **NET_ADAPTER_PAUSE_FUNCTIONS** enumeration is used to specify pause frame support in the [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

An initialized [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure is an input to [NetAdapterSetLinkState](nf-netadapter-netadaptersetlinkstate.md).



## -see-also
