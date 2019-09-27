---
UID: NS:virtualaddresstypes._NET_FRAGMENT_VIRTUAL_ADDRESS
title: NET_FRAGMENT_VIRTUAL_ADDRESS (virtualaddresstypes.h)
author: windows-driver-content
description: The NET_FRAGMENT_VIRTUAL_ADDRESS structure contains data buffer information for a NET_FRAGMENT.
tech.root: netvista
ms.assetid: 6D9E0986-50FF-4CDC-B5F3-475047DD5699
ms.author: windowsdriverdev
ms.date: 09/26/2019
ms.topic: struct
f1_keywords:
 - "virtualaddresstypes/NET_FRAGMENT_VIRTUAL_ADDRESS"
ms.keywords: NET_FRAGMENT_VIRTUAL_ADDRESS, NET_FRAGMENT_VIRTUAL_ADDRESS, 
req.header: virtualaddresstypes.h
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
req.typenames: NET_FRAGMENT_VIRTUAL_ADDRESS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - virtualaddresstypes.h
api_name: 
 - NET_FRAGMENT_VIRTUAL_ADDRESS
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_FRAGMENT_VIRTUAL_ADDRESS structure

## -description

The **NET_FRAGMENT_VIRTUAL_ADDRESS** structure contains payload buffer information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -struct-fields

### -field VirtualAddress

Points to the start of the packet buffer. This address is mapped into the system address space.

For transmit queues, this value is read-only.

## -remarks

To obtain this structure, call [**NetExtensionGetFragmentVirtualAddress**](../virtualaddress/nf-virtualaddress-netextensiongetfragmentvirtualaddress.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentVirtualAddress**](../virtualaddress/nf-virtualaddress-netextensiongetfragmentvirtualaddress.md)