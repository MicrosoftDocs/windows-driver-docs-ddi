---
UID: NS:kdnetpf._NDIS_KDNET_ADD_PF
tech.root: debugger
title: NDIS_KDNET_ADD_PF (kdnetpf.h)
ms.date: 07/27/2023
targetos: Windows
description: "Learn more about the KDNETPF transport support API - _NDIS_KDNET_ADD_PF" 
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
req.typenames: NDIS_KDNET_ADD_PF, *PNDIS_KDNET_ADD_PF
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
 - _NDIS_KDNET_ADD_PF
 - PNDIS_KDNET_ADD_PF
 - NDIS_KDNET_ADD_PF
f1_keywords:
 - _NDIS_KDNET_ADD_PF
 - kdnetpf/_NDIS_KDNET_ADD_PF
 - PNDIS_KDNET_ADD_PF
 - kdnetpf/PNDIS_KDNET_ADD_PF
 - NDIS_KDNET_ADD_PF
 - kdnetpf/NDIS_KDNET_ADD_PF
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_ADD_PF
---

## -description

The **NDIS_KDNET_ADD_PF** structure describes the data required to add a PF to the BDF port. It is used by OID_KDNET_ADD_PF.

## -struct-fields

### -field Header

A [NDIS_OBJECT_HEADER structure](/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header) used to package the object type, version, and size information that is required in many NDIS 6.0 structures.

### -field AddedFunctionNumber

One element containing the added PF port number.

## -remarks

## -see-also

[kdnetpf.h](kdnetpf.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
