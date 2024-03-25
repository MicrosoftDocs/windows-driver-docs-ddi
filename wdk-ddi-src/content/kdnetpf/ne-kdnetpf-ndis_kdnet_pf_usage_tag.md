---
UID: NE:kdnetpf._NDIS_KDNET_PF_USAGE_TAG
tech.root: debugger
title: NDIS_KDNET_PF_USAGE_TAG (kdnetpf.h)
ms.date: 08/21/2023
targetos: Windows
description: "The KDNETPF transport support NDIS_KDNET_PF_USAGE_TAG enumeration defines the PF usage." 
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: kdnetpf.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - kdnetpf.h
api_name:
 - _NDIS_KDNET_PF_USAGE_TAG
 - PNDIS_KDNET_PF_USAGE_TAG
 - NDIS_KDNET_PF_USAGE_TAG
f1_keywords:
 - _NDIS_KDNET_PF_USAGE_TAG
 - kdnetpf/_NDIS_KDNET_PF_USAGE_TAG
 - PNDIS_KDNET_PF_USAGE_TAG
 - kdnetpf/PNDIS_KDNET_PF_USAGE_TAG
 - NDIS_KDNET_PF_USAGE_TAG
 - kdnetpf/NDIS_KDNET_PF_USAGE_TAG
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_PF_USAGE_TAG
---

## -description

The **NDIS_KDNET_PF_USAGE_TAG** enumeration defines the PF usage. It is ued to indicate the entity that owns the PF.
It is used by [NDIS_KDNET_QUERY_PF_INFORMATION](ns-kdnetpf-ndis_kdnet_query_pf_information.md).

## -enum-fields

### -field NdisKdnetPfUsageUnknown

The usage is unknown.

### -field NdisKdnetPfUsageKdModule

The usage is a KdModule.

## -remarks

## -see-also

[kdnetpf.h](index.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
