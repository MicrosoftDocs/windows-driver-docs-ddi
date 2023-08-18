---
UID: NS:kdnetpf._NDIS_KDNET_QUERY_PF_INFORMATION
tech.root: debugger
title: NDIS_KDNET_QUERY_PF_INFORMATION (kdnetpf.h)
ms.date: 08/18/2023
targetos: Windows
description: "KDNETPF transport support API - The NDIS_KDNET_QUERY_PF_INFORMATION structure describes the data required to query the PF management data." 
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
req.typenames: NDIS_KDNET_QUERY_PF_INFORMATION, *PNDIS_KDNET_QUERY_PF_INFORMATION
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
 - _NDIS_KDNET_QUERY_PF_INFORMATION
 - PNDIS_KDNET_QUERY_PF_INFORMATION
 - NDIS_KDNET_QUERY_PF_INFORMATION
f1_keywords:
 - _NDIS_KDNET_QUERY_PF_INFORMATION
 - kdnetpf/_NDIS_KDNET_QUERY_PF_INFORMATION
 - PNDIS_KDNET_QUERY_PF_INFORMATION
 - kdnetpf/PNDIS_KDNET_QUERY_PF_INFORMATION
 - NDIS_KDNET_QUERY_PF_INFORMATION
 - kdnetpf/NDIS_KDNET_QUERY_PF_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_QUERY_PF_INFORMATION
---

## -description

The **NDIS_KDNET_QUERY_PF_INFORMATION** structure describes the data required to query the PF management data.

It is used by OID_KDNET_QUERY_PF_INFORMATION.

## -struct-fields

### -field Header

A [NDIS_OBJECT_HEADER structure](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header) used to package the object type, version, and size information that is required in many NDIS 6.0 structures.

### -field Bdf

The PF PCI location to query for.

### -field NetworkAdddress[6]

The PF assigned MAC address.

### -field UsageTag

The PF Usage tag described by [NDIS_KDNET_PF_USAGE_TAG](ne-kdnetpf-ndis_kdnet_pf_usage_tag.md).

### -field MaximumNumberOfSupportedPfs

The maximum number of Pfs that can be associated to the Primary BDF.
  
### -field DeviceId

The KDNET PF device ID. It is used if there is a new added PF and the FW assigns a new DeviceID to the added KDNET PF.

## -remarks

## -see-also

[kdnetpf.h](index.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
