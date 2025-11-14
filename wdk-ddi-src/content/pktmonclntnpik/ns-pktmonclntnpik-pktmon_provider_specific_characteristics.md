---
UID: NS:pktmonclntnpik._PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
tech.root: netvista
title: PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS structure contains version information and characteristics specific to a Packet Monitor provider implementation.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
 - PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
f1_keywords:
 - _PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
 - pktmonclntnpik/_PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
 - PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
 - pktmonclntnpik/PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS
---

## -description

The **PKTMON_PROVIDER_SPECIFIC_CHARACTERISTICS** structure contains version information and characteristics specific to a Packet Monitor provider implementation. This structure is used during provider initialization to communicate provider capabilities and versioning information.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md) structure used for versioning and size validation.

### -field ProviderMajorVersion

The major version number of the provider implementation. This is used to ensure compatibility between the provider and clients.

### -field ProviderMinorVersion

The minor version number of the provider implementation. This indicates incremental updates or feature additions within the same major version.

## -remarks

Providers use this structure to advertise their version and capabilities to the monitoring infrastructure, enabling version negotiation and feature detection.

## -see-also

- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PKTMON_CLIENT_DISPATCH](ns-pktmonclntnpik-pktmon_client_dispatch.md)
- [PktMonClntInitialize](../pktmonclntk/nf-pktmonclntk-pktmonclntinitialize.md)

