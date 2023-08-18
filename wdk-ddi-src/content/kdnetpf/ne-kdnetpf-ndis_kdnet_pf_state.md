---
UID: NE:kdnetpf._NDIS_KDNET_PF_STATE
tech.root: debugger
title: NDIS_KDNET_PF_STATE (kdnetpf.h)
ms.date: 08/18/2023
targetos: Windows
description: "KDNETPF transport support API - The NDIS_KDNET_PF_STATE enumeration defines the PF state." 
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
 - _NDIS_KDNET_PF_STATE
 - PNDIS_KDNET_PF_STATE
 - NDIS_KDNET_PF_STATE
f1_keywords:
 - _NDIS_KDNET_PF_STATE
 - kdnetpf/_NDIS_KDNET_PF_STATE
 - PNDIS_KDNET_PF_STATE
 - kdnetpf/PNDIS_KDNET_PF_STATE
 - NDIS_KDNET_PF_STATE
 - kdnetpf/NDIS_KDNET_PF_STATE
dev_langs:
 - c++
helpviewer_keywords:
 - _NDIS_KDNET_PF_STATE
---

## -description

The **NDIS_KDNET_PF_STATE** enumeration defines the PF state.

## -enum-fields

### -field NdisKdNetPfStatePrimary

This is a primary PF and it's usually used only by the miniport driver.

### -field NdisKdnetPfStateEnabled

This is an added secondary PF, that is used by KDNET.

### -field NdisKdnetPfStateConfigured

This is an added PF, but it is only added/configured and is not used.

## -remarks

## -see-also

[kdnetpf.h](index.md)

[Debugger 2PF KDNET Support](/windows-hardware/drivers/network/debugger-2pf-kdnet-support)
