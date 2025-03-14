---
UID: NE:pktmondefk._PKTMON_COMPONENT_TYPE
tech.root: 
title: PKTMON_COMPONENT_TYPE
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_COMPONENT_TYPE enum defines the various component types that can be registered with Packet Monitor.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: pktmondefk.h
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
 - pktmondefk.h
api_name:
 - _PKTMON_COMPONENT_TYPE
 - PKTMON_COMPONENT_TYPE
f1_keywords:
 - _PKTMON_COMPONENT_TYPE
 - pktmondefk/_PKTMON_COMPONENT_TYPE
 - PKTMON_COMPONENT_TYPE
 - pktmondefk/PKTMON_COMPONENT_TYPE
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_COMPONENT_TYPE
---

## -description

The **PKTMON_COMPONENT_TYPE** enum defines the various component types that can be registered with Packet Monitor.

## -enum-fields

### -field PktMonComp_Ndis

Corresponds to the NDIS component type.

### -field PktMonComp_Miniport

Corresponds to the Miniport component type.

### -field PktMonComp_Filter

Corresponds to the Filter component type.

### -field PktMonComp_Protocol

Corresponds to the Protocol component type.

### -field PktMonComp_VmsVmNic

Corresponds to the VmsVmNic component type.

### -field PktMonComp_VmsMiniport

Corresponds to the VmsMiniport component type.

### -field PktMonComp_VmsExtMiniport

Corresponds to the VmsExtMiniport component type.

### -field PktMonComp_VmsProtocolNic

Corresponds to the VmsProtocolNic component type.

### -field PktMonComp_NetVsc

Corresponds to the NetVsc component type.

### -field PktMonComp_HTTP

Corresponds to the HTTP component type.

### -field PktMonComp_IpInterface

Corresponds to the IpInterface component type.

### -field PktMonComp_Slbmux

Corresponds to the Slbmux component type.

### -field PktMonComp_Ipsec

Corresponds to the Ipsec component type.

### -field PktMonComp_NetCx

Corresponds to the NetCx component type.

### -field PktMonComp_HTTPMessage

Corresponds to the HTTPMessage component type.

## -remarks

## -see-also

- [PktMonClntComponentRegister](../pktmonclntk/nc-pktmonclntk-pktmon_clnt_component_register.md)
