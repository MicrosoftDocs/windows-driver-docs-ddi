---
UID: NE:netadapter._NET_ADAPTER_PAUSE_FUNCTION_TYPE
title: NET_ADAPTER_PAUSE_FUNCTION_TYPE (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_PAUSE_FUNCTION_TYPE enumeration specifies what IEEE 802.3 pause frames a net adapter supports.
tech.root: netvista
ms.assetid: a8049bd4-c346-4cf4-b1c3-d4e01a3b7862
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NET_ADAPTER_PAUSE_FUNCTION_TYPE enumeration"]
f1_keywords:
 - "netadapter/NET_ADAPTER_PAUSE_FUNCTION_TYPE"
 - "NET_ADAPTER_PAUSE_FUNCTION_TYPE"
ms.keywords: NET_ADAPTER_PAUSE_FUNCTION_TYPE, NET_ADAPTER_PAUSE_FUNCTION_TYPE, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: NET_ADAPTER_PAUSE_FUNCTION_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - netadapter.h
api_name: 
 - NET_ADAPTER_PAUSE_FUNCTION_TYPE
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_ADAPTER_PAUSE_FUNCTION_TYPE enumeration

## -description

The **NET_ADAPTER_PAUSE_FUNCTION_TYPE** enumeration specifies what IEEE 802.3 pause frames a net adapter supports.

## -enum-fields

### -field NetAdapterPauseFunctionTypeUnsupported 

Indicates that the adapter or link partner does not support pause frames.

### -field NetAdapterPauseFunctionTypeSendOnly 

Indicates that the adapter and link partner only support sending pause frames from the adapter to the link partner.

### -field NetAdapterPauseFunctionTypeReceiveOnly 

Indicates that the adapter and link partner only support sending pause frames from the link partner to the adapter.

### -field NetAdapterPauseFunctionTypeSendAndReceive 

Indicates that the adapter and link partner support sending and receiving pause frames in both transint and receive directions.

### -field NetAdapterPauseFunctionTypeUnknown 

Indicates that pause frame negotiation is in progress. The pause frame support that the link partner provides is unknown.

## -remarks

This enumeration is a member of the [**NET_ADAPTER_LINK_STATE**](../netadapter/ns-netadapter-_net_adapter_link_state.md) structure.

## -see-also

[**NET_ADAPTER_LINK_STATE**](../netadapter/ns-netadapter-_net_adapter_link_state.md)
