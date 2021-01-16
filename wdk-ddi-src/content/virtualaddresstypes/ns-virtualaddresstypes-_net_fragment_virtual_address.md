---
UID: NS:virtualaddresstypes._NET_FRAGMENT_VIRTUAL_ADDRESS
title: NET_FRAGMENT_VIRTUAL_ADDRESS (virtualaddresstypes.h)
description: The NET_FRAGMENT_VIRTUAL_ADDRESS structure contains data buffer information for a NET_FRAGMENT.
tech.root: netvista
ms.date: 09/26/2019
keywords: ["NET_FRAGMENT_VIRTUAL_ADDRESS structure"]
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_FRAGMENT_VIRTUAL_ADDRESS
 - virtualaddresstypes/_NET_FRAGMENT_VIRTUAL_ADDRESS
 - NET_FRAGMENT_VIRTUAL_ADDRESS
 - virtualaddresstypes/NET_FRAGMENT_VIRTUAL_ADDRESS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - virtualaddresstypes.h
api_name:
 - _NET_FRAGMENT_VIRTUAL_ADDRESS
 - NET_FRAGMENT_VIRTUAL_ADDRESS
product:
 - Windows
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

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentVirtualAddress**](../virtualaddress/nf-virtualaddress-netextensiongetfragmentvirtualaddress.md)

