---
UID: NS:kdnetpf._NDIS_KDNET_ENUMERATE_PFS
tech.root: debugger
title: NDIS_KDNET_ENUMERATE_PFS (kdnetpf.h)
ms.date: 08/18/2023
targetos: Windows
description: "Learn more about the KDNETPF transport support API -The NDIS_KDNET_ENUMERATE_PFS structure describes the data required to enumerate the list of PF." 
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
req.typenames: NDIS_KDNET_ENUMERATE_PFS, *PNDIS_KDNET_ENUMERATE_PFS
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
 - _NDIS_KDNET_ENUMERATE_PFS
 - PNDIS_KDNET_ENUMERATE_PFS
 - NDIS_KDNET_ENUMERATE_PFS
f1_keywords:
 - _NDIS_KDNET_ENUMERATE_PFS
 - kdnetpf/_NDIS_KDNET_ENUMERATE_PFS
 - PNDIS_KDNET_ENUMERATE_PFS
 - kdnetpf/PNDIS_KDNET_ENUMERATE_PFS
 - NDIS_KDNET_ENUMERATE_PFS
 - kdnetpf/NDIS_KDNET_ENUMERATE_PFS
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_ENUMERATE_PFS
---

## -description

The **NDIS_KDNET_ENUMERATE_PFS**  structure describes the data required to enumerate the list of PF. It is used by OID_KDNET_ENUMERATE_PFS.

## -struct-fields

### -field Header

A [NDIS_OBJECT_HEADER structure](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header) used to package the object type, version, and size information that is required in many NDIS 6.0 structures.

### -field ElementSize

The size of each element is the sizeof(NDIS_KDNET_PF_ENUM_ELEMENT).

### -field NumberOfElements

The number of elements in the returned array.

### -field OffsetToFirstElement

Offset value to the first element of the returned array. Each array element is defined by [NDIS_KDNET_PF_ENUM_ELEMENT](ns-kdnetpf-ndis_kdnet_pf_enum_element.md).

## -remarks

## -see-also

[kdnetpf.h](kdnetpf.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
