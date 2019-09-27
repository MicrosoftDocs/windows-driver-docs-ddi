---
UID: NF:logicaladdress.NetExtensionGetFragmentLogicalAddress
title: NetExtensionGetFragmentLogicalAddress function (logicaladdress.h)
author: windows-driver-content
description: The NetExtensionGetFragmentLogicalAddress method retrieves the DMA logical address extension information for a net fragment.
tech.root: netvista
ms.assetid: 8ED86035-A4B3-47C5-A138-1164B5A58291
ms.author: windowsdriverdev
ms.date: 09/26/2019
ms.topic: function
f1_keywords:
 - "logicaladdress/NetExtensionGetFragmentLogicalAddress"
ms.keywords: NetExtensionGetFragmentLogicalAddress
req.header: logicaladdress.h
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- logicaladdress.h
api_name: 
- NetExtensionGetFragmentLogicalAddress
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetExtensionGetFragmentLogicalAddress function

## -description

The **NetExtensionGetFragmentLogicalAddress** method retrieves the DMA logical address extension information for a net fragment.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the DMA logical address extension information for this fragment.

### -param Index

The index in the fragment ring for the target [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -returns

Returns a pointer to a [**NET_FRAGMENT_LOGICAL_ADDRESS**](../logicaladdresstypes/ns-logicaladdresstypes-_net_fragment_logical_address.md) structure that contains the DMA logical address for the fragment.

## -remarks

NIC client drivers typically query offsets for fragment extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the DMA logical address offset from the queue context to pass to **NetExtensionGetFragmentLogicalAddress**.

This method is a wrapper method around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md). 

## -see-also

[Transmit and receive queues](https://docs.microsoft.com/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)