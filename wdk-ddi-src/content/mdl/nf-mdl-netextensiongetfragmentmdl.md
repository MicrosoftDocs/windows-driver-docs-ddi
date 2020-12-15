---
UID: NF:mdl.NetExtensionGetFragmentMdl
title: NetExtensionGetFragmentMdl function (mdl.h)
description: The NetExtensionGetFragmentMdl function retrieves the DMA MDL extension information for a net fragment.
tech.root: netvista
ms.date: 09/26/2019
keywords: ["NetExtensionGetFragmentMdl function"]
ms.keywords: NetExtensionGetFragmentMdl
req.header: mdl.h
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
 - NetExtensionGetFragmentMdl
 - mdl/NetExtensionGetFragmentMdl
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - mdl.h
api_name:
 - NetExtensionGetFragmentMdl
product:
 - Windows
---

# NetExtensionGetFragmentMdl function


## -description

The **NetExtensionGetFragmentMdl** function retrieves the DMA MDL extension information for a net fragment.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the DMA MDL extension information for this fragment.

### -param Index

The index in the fragment ring for the target [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -returns

Returns a pointer to a [**NET_FRAGMENT_MDL**](../mdltypes/ns-mdltypes-_net_fragment_mdl.md) structure that contains the DMA MDL information for the fragment.

## -remarks

NIC client drivers typically query offsets for fragment extensions during datapath queue creation, then store them in their queue context space so they don't have to query them too often. For an example of this, see [Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues). Clients can retrieve the DMA MDL offset from the queue context to pass to **NetExtensionGetFragmentMdl**.

This function is a wrapper function around [**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md).

## -see-also

[Transmit and receive queues](/windows-hardware/drivers/netcx/transmit-and-receive-queues)

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NetExtensionGetData**](../extension/nf-extension-netextensiongetdata.md)
