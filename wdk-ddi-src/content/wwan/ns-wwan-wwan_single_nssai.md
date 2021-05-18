---
UID: NS:wwan._WWAN_SINGLE_NSSAI
tech.root: 
title: WWAN_SINGLE_NSSAI
ms.date: 
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_SINGLE_NSSAI, *PWWAN_SINGLE_NSSAI
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SINGLE_NSSAI
 - PWWAN_SINGLE_NSSAI
 - WWAN_SINGLE_NSSAI
f1_keywords:
 - _WWAN_SINGLE_NSSAI
 - wwan/_WWAN_SINGLE_NSSAI
 - PWWAN_SINGLE_NSSAI
 - wwan/PWWAN_SINGLE_NSSAI
 - WWAN_SINGLE_NSSAI
 - wwan/WWAN_SINGLE_NSSAI
dev_langs:
 - c++
---

## -description

The WWAN_SINGLE_NSSAI structure represents a single Network Slice Selection Assistance Information (NSSAI). WWAN_SINGLE_NSSAI is used to uniquely identify a network slice.

## -struct-fields

### -field Bitmasks

A 32-bit integer containing the map (logical OR) indicating if the fields that follow are present.

### -field SliceServiceType

Only valid if *Bitmasks* contains WWAN_SNSSAI_SST_VALID (0x00000001).

### -field MappedSliceServiceType

Only valid if *Bitmasks* contains WWAN_SNSSAI_MAPPED_SST_VALID (0x00000002).

### -field SliceDifferentiator

Only valid if *SliceServiceType* is valid. May be WWAN_SNSSAI_NO_SD_VALUE_ASSOCIATED_WITH_SST (0x00FFFFFF).

Defines the expected behavior of the network slice features and services. Values include enhanced mobile broadband (eMBB), ultra-reliable low latency communications (URLLC), and massive Internet of Things (MIoT).

### -field MappedSliceDifferentiator

Only valid if *MappedSliceServiceType* is valid. May be WWAN_SNSSAI_NO_SD_VALUE_ASSOCIATED_WITH_SST (0x00FFFFFF).

The slice differentiator is directly related to the *SliceServiceType* and is used as an additional differentiator if multiple network slices carry the same value in *SliceServiceType*.

## -remarks

## -see-also

[WWAN_CONTEXT_STATE](/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_context_state)
