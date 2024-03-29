---
UID: NS:mdltypes._NET_FRAGMENT_MDL
title: NET_FRAGMENT_MDL (mdltypes.h)
description: The NET_FRAGMENT_MDL structure contains DMA MDL information for a NET_FRAGMENT.
tech.root: netvista
ms.date: 09/26/2019
keywords: ["NET_FRAGMENT_MDL structure"]
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
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_FRAGMENT_MDL
 - mdltypes/_NET_FRAGMENT_MDL
 - NET_FRAGMENT_MDL
 - mdltypes/NET_FRAGMENT_MDL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - mdltypes.h
api_name:
 - _NET_FRAGMENT_MDL
 - NET_FRAGMENT_MDL
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

[Packet descriptors and extensions](/windows-hardware/drivers/netcx/packet-descriptors-and-extensions)

[**NET_FRAGMENT**](../fragment/ns-fragment-_net_fragment.md)

[**NetExtensionGetFragmentMdl**](../mdl/nf-mdl-netextensiongetfragmentmdl.md)

