---
UID: NF:ndis.NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE
title: NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE macro (ndis.h)
description: Hyper-V extensible switch extensions use the NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE macro to define the context type that is used by the SetNetBufferListSwitchContext and GetNetBufferListSwitchContext functions to attach and retrieve context from a NET_BUFFER_LIST structure. Extensions can define as many context types as they want within their driver.
tech.root: netvista
ms.assetid: bde251f3-a9b1-4f9f-b7ff-4a7ac71be99d
ms.date: 04/17/2018
keywords: ["NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE macro"]
f1_keywords:
 - "ndis/NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE"
ms.keywords: NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE
req.header: ndis.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- ndis.h
api_name: 
- NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE
product:
- Windows
targetos: Windows

---

# NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE macro


## -description

Hyper-V extensible switch extensions use the **NDIS_DECLARE_SWITCH_NET_BUFFER_LIST_CONTEXT_TYPE** macro to define the context type that is used by the [*SetNetBufferListSwitchContext*](nc-ndis-ndis_switch_set_net_buffer_list_switch_context.md) and [*GetNetBufferListSwitchContext*](nc-ndis-ndis_switch_get_net_buffer_list_switch_context.md) functions to attach and retrieve context from a [**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md) structure. Extensions can define as many context types as they want within their driver.

## -parameters

### -param _ContextName

An identifier for the context type.

### -param _ExtensionId

A GUID that matches the extension ID.

## -remarks

## -see-also

[*SetNetBufferListSwitchContext*](nc-ndis-ndis_switch_set_net_buffer_list_switch_context.md)

[*GetNetBufferListSwitchContext*](nc-ndis-ndis_switch_get_net_buffer_list_switch_context.md)

[**NET_BUFFER_LIST**](ns-ndis-_net_buffer_list.md)
