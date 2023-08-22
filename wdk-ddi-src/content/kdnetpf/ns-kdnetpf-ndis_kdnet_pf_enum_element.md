---
UID: NS:kdnetpf._NDIS_KDNET_PF_ENUM_ELEMENT
tech.root: debugger
title: NDIS_KDNET_PF_ENUM_ELEMENT (kdnetpf.h)
ms.date: 08/22/2023
targetos: Windows
description: "KDNETPF transport support API NDIS_KDNET_PF_ENUM_ELEMENT is a PF element array structure." 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: kdnetpf.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_KDNET_PF_ENUM_ELEMENT, *PNDIS_KDNET_PF_ENUM_ELEMENT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - kdnetpf.h
api_name:
 - _NDIS_KDNET_PF_ENUM_ELEMENT
 - PNDIS_KDNET_PF_ENUM_ELEMENT
 - NDIS_KDNET_PF_ENUM_ELEMENT
f1_keywords:
 - _NDIS_KDNET_PF_ENUM_ELEMENT
 - kdnetpf/_NDIS_KDNET_PF_ENUM_ELEMENT
 - PNDIS_KDNET_PF_ENUM_ELEMENT
 - kdnetpf/PNDIS_KDNET_PF_ENUM_ELEMENT
 - NDIS_KDNET_PF_ENUM_ELEMENT
 - kdnetpf/NDIS_KDNET_PF_ENUM_ELEMENT
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_PF_ENUM_ELEMENT
---

## -description

The **NDIS_KDNET_PF_ENUM_ELEMENT** is a PF element array structure.

## -struct-fields

### -field Header

A [NDIS_OBJECT_HEADER structure](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header) used to package the object type, version, and size information that is required in many NDIS 6.0 structures.

### -field PfNumber

The PF value (e.g. if `<bus.dev.fun>`, then PF value = fun).

### -field PfState

The PF state value defined by [NDIS_KDNET_PF_STATE](ne-kdnetpf-ndis_kdnet_pf_state.md).

## -remarks

## -see-also

[kdnetpf.h](index.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
