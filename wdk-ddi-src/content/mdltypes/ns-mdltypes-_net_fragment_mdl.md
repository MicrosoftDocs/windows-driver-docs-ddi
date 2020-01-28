---
UID: NS:mdltypes._NET_FRAGMENT_MDL
title: NET_FRAGMENT_MDL (mdltypes.h)
author: windows-driver-content
description: The NET_FRAGMENT_MDL structure contains DMA MDL information for a NET_FRAGMENT.
tech.root: netvista
ms.assetid: DA25E9D1-BCAC-4B48-9F13-A5C673CF40D3
ms.author: windowsdriverdev
ms.date: 09/26/2019
f1_keywords:
 - "mdltypes/NET_FRAGMENT_MDL"
ms.keywords: NET_FRAGMENT_MDL, NET_FRAGMENT_MDL, 
req.header: mdltypes.h
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
req.typenames: NET_FRAGMENT_MDL
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - mdltypes.h
api_name: 
 - NET_FRAGMENT_MDL
product: 
 - Windows
targetos: Windows
ms.custom: Vb
---

# NET_FRAGMENT_MDL structure

## -description

The **NET_FRAGMENT_MDL** structure contains DMA MDL information for a [**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md).

## -struct-fields

### -field Mdl

For transmit queues, a pointer to an MDL to be used for scatter/gather DMA.

For receive queues, this member is not used.

Do not modify this value. 

## -remarks

To obtain this structure, call [**NetExtensionGetFragmentMdl**](../mdl/nf-mdl-netextensiongetfragmentmdl.md).

## -see-also

[Packet descriptors and extensions](https://docs.microsoft.com/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentMdl**](../mdl/nf-mdl-netextensiongetfragmentmdl.md)
