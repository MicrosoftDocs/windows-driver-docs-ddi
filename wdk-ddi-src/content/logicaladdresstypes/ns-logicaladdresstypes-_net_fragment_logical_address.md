---
UID: NS:logicaladdresstypes._NET_FRAGMENT_LOGICAL_ADDRESS
title: NET_FRAGMENT_LOGICAL_ADDRESS (logicaladdresstypes.h)
author: windows-driver-content
description: The NET_FRAGMENT_LOGICAL_ADDRESS structure contains DMA logical address information for a NET_FRAGMENT.
tech.root: netvista
ms.assetid: 9E757066-6A96-41DF-8185-3264E5076651
ms.author: windowsdriverdev
ms.date: 09/26/2019
f1_keywords:
 - "logicaladdresstypes/NET_FRAGMENT_LOGICAL_ADDRESS"
ms.keywords: NET_FRAGMENT_LOGICAL_ADDRESS, NET_FRAGMENT_LOGICAL_ADDRESS, 
req.header: logicaladdresstypes.h
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
req.typenames: NET_FRAGMENT_LOGICAL_ADDRESS
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - logicaladdresstypes.h
api_name: 
 - NET_FRAGMENT_LOGICAL_ADDRESS
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_FRAGMENT_LOGICAL_ADDRESS structure

## -description

The **NET_FRAGMENT_LOGICAL_ADDRESS** structure contains DMA logical address information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -struct-fields

### -field LogicalAddress

For receive queues, contains a mapped DMA address that can be used to program NIC hardware.

For transmit queues, cast this value to an MDL pointer.

Do not modify this value.

## -remarks

To obtain this structure, call [**NetExtensionGetFragmentLogicalAddress**](../logicaladdress/nf-logicaladdress-netextensiongetfragmentlogicaladdress.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentLogicalAddress**](../logicaladdress/nf-logicaladdress-netextensiongetfragmentlogicaladdress.md)
