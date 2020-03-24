---
UID: NS:returncontexttypes._NET_FRAGMENT_RETURN_CONTEXT
title: NET_FRAGMENT_RETURN_CONTEXT (returncontexttypes.h)
author: windows-driver-content
description: The NET_FRAGMENT_RETURN_CONTEXT structure contains return context information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).
tech.root: netvista
ms.assetid: 5795F982-866D-4731-BE0E-A085B0254CDF
ms.author: windowsdriverdev
ms.date: 09/26/2019
keywords: ["NET_FRAGMENT_RETURN_CONTEXT structure"]
f1_keywords:
 - "returncontexttypes/NET_FRAGMENT_RETURN_CONTEXT"
ms.keywords: NET_FRAGMENT_RETURN_CONTEXT, NET_FRAGMENT_RETURN_CONTEXT, 
req.header: returncontexttypes.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_FRAGMENT_RETURN_CONTEXT
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - returncontexttypes.h
api_name: 
 - NET_FRAGMENT_RETURN_CONTEXT
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_FRAGMENT_RETURN_CONTEXT structure

## -description

The **NET_FRAGMENT_RETURN_CONTEXT** structure contains return context information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -struct-fields

### -field Handle

A handle to a driver-allocated context space structure.

For more information about receive path capabilities, see [**NET_ADAPTER_RX_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_rx_capabilities.md). 

## -remarks

To obtain this structure, call [**NetExtensionGetFragmentReturnContext**](../returncontext/nf-returncontext-netextensiongetfragmentreturncontext.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentReturnContext**](../returncontext/nf-returncontext-netextensiongetfragmentreturncontext.md)
