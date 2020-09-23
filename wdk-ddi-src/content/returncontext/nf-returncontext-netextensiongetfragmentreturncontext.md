---
UID: NF:returncontext.NetExtensionGetFragmentReturnContext
title: NetExtensionGetFragmentReturnContext function (returncontext.h)
description: The NetExtensionGetFragmentReturnContext function retrieves the return context extension information for a net fragment.
tech.root: netvista
ms.assetid: 057827CD-03DD-429D-9DDF-7846D344DC88
ms.author: windowsdriverdev
ms.date: 09/26/2019
keywords: ["NetExtensionGetFragmentReturnContext function"]
ms.keywords: NetExtensionGetFragmentReturnContext
req.header: returncontext.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetExtensionGetFragmentReturnContext
 - returncontext/NetExtensionGetFragmentReturnContext
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - returncontext.h
api_name:
 - NetExtensionGetFragmentReturnContext
product:
 - Windows
---

# NetExtensionGetFragmentReturnContext function


## -description

The **NetExtensionGetFragmentReturnContext** function retrieves the return context extension information for a net fragment.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the return context extension information for this fragment.

### -param Index

The index in the fragment ring for the target [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -returns

Returns a pointer to a [**NET_FRAGMENT_RETURN_CONTEXT**](../returncontexttypes/ns-returncontexttypes-_net_fragment_return_context.md) structure that contains the return context information for the fragment.

## -remarks

NIC client drivers typically query offsets for fragment extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the return context offset from the queue context to pass to **NetExtensionGetFragmentReturnContext**.

This function is a wrapper function around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md).

## -see-also

[Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)

