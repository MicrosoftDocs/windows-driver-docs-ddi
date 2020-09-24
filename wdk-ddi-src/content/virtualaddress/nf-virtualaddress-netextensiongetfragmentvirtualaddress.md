---
UID: NF:virtualaddress.NetExtensionGetFragmentVirtualAddress
title: NetExtensionGetFragmentVirtualAddress function (virtualaddress.h)
description: The NetExtensionGetFragmentVirtualAddress function retrieves the virtual address extension information for a net fragment.
tech.root: netvista
ms.assetid: 054DB38D-7496-424F-A521-A2368878F690
ms.date: 09/26/2019
keywords: ["NetExtensionGetFragmentVirtualAddress function"]
ms.keywords: NetExtensionGetFragmentVirtualAddress
req.header: virtualaddress.h
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
 - NetExtensionGetFragmentVirtualAddress
 - virtualaddress/NetExtensionGetFragmentVirtualAddress
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - virtualaddress.h
api_name:
 - NetExtensionGetFragmentVirtualAddress
product:
 - Windows
---

# NetExtensionGetFragmentVirtualAddress function


## -description

The **NetExtensionGetFragmentVirtualAddress** function retrieves the virtual address extension information for a net fragment.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the virtual address extension information for this fragment.

### -param Index

The index in the fragment ring for the target [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -returns

Returns a pointer to a [**NET_FRAGMENT_VIRTUAL_ADDRESS**](../virtualaddresstypes/ns-virtualaddresstypes-_net_fragment_virtual_address.md) structure that contains the virtual address information for the fragment.

## -remarks

NIC client drivers typically query offsets for fragment extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the virtual address offset from the queue context to pass to **NetExtensionGetFragmentVirtualAddress**.

This function is a wrapper function around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md).

## -see-also

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)