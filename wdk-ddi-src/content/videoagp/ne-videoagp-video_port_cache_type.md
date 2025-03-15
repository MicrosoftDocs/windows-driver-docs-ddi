---
UID: NE:videoagp.VIDEO_PORT_CACHE_TYPE
tech.root: display
title: VIDEO_PORT_CACHE_TYPE
ms.date: 11/01/2024
targetos: Windows
description: Learn more about VIDEO_PORT_CACHE_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: videoagp.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - videoagp.h
api_name:
 - VIDEO_PORT_CACHE_TYPE
f1_keywords:
 - VIDEO_PORT_CACHE_TYPE
 - videoagp/VIDEO_PORT_CACHE_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - VIDEO_PORT_CACHE_TYPE
---

## -description

The **VIDEO_PORT_CACHE_TYPE** enumeration specifies the type of caching that the system should use.

## -enum-fields

### -field VpNonCached

The system should not cache the range of addresses.

### -field VpWriteCombined

The system should use write-combined (WC) caching. For information about WC caching, see the [Write-Combining Memory in Video Miniport Drivers](/previous-versions/windows/hardware/design/dn642116(v=vs.85)).

### -field VpCached

The system should use oridinary caching.

## -see-also

[**AgpReservePhysical**](nc-videoagp-pagp_reserve_physical.md)
