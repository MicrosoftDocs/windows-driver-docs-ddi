---
UID: NS:pktmonnetevtnpik._PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
tech.root: netvista
title: PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
ms.date: 11/12/2025
targetos: Windows
description: Defines the characteristics of a Packet Monitor NetEvt NMR provider module.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnetevtnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnetevtnpik.h
api_name:
 - _PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
 - PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
f1_keywords:
 - _PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
 - pktmonnetevtnpik/_PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
 - PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
 - pktmonnetevtnpik/PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_PROVIDER_CHARACTERISTICS
---

## -description

The **PKTMON_NETEVT_PROVIDER_CHARACTERISTICS** structure defines the characteristics of a Packet Monitor NetEvt NMR provider module. This structure is used during provider registration to describe the provider's capabilities and properties to the Network Module Registrar (NMR).

## -struct-fields

### -field Header

A **[PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md)** structure containing version and size information for this characteristics structure. The *Header* field ensures proper structure versioning and compatibility between provider and client modules.

## -remarks

Provider modules populate this structure when registering with the NMR to advertise their capabilities. The structure must remain valid and resident in memory as long as the provider is registered with the NMR.

## -see-also

- [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md)
- [PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnetevtnpik-pktmon_netevt_provider_dispatch.md)
- [NmrRegisterProvider](/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrregisterprovider)

