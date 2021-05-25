---
UID: NS:wwan._WWAN_REJECTED_SNSSAI
tech.root: 
title: WWAN_REJECTED_SNSSAI
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
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_REJECTED_SNSSAI, *PWWAN_REJECTED_SNSSAI
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_REJECTED_SNSSAI
 - PWWAN_REJECTED_SNSSAI
 - WWAN_REJECTED_SNSSAI
f1_keywords:
 - _WWAN_REJECTED_SNSSAI
 - wwan/_WWAN_REJECTED_SNSSAI
 - PWWAN_REJECTED_SNSSAI
 - wwan/PWWAN_REJECTED_SNSSAI
 - WWAN_REJECTED_SNSSAI
 - wwan/WWAN_REJECTED_SNSSAI
dev_langs:
 - c++
---

## -description

The WWAN_REJECTED_SNSSAI structure contains information about a single Network Slice Selection Assistance Information (S-NSSAI) that was rejected.

## -struct-fields

### -field CauseCode

A 16-bit integer containing a standardized code indicating why the S-NSSAI was rejected.

### -field SliceServiceType

The *SliceServiceType* field may have standardized and non-standardized values. The standardized range contains values from 0 to 127. The operator-specific range contains values from 128 to 255.

| Standardized value | Description |
|--- |--- |
| 1 | Enhanced mobile broadband |
| 2 | Ultra-reliable low latency communications |
| 3 | Massive Internet of Things (IoT) |

### -field SliceDifferentiator

The *SliceDifferentiator* field is optional information that complements the *SliceServiceType* to differentiate among multiple network slices.

If not specified this will be WWAN_SNSSAI_NO_SD_VALUE_ASSOCIATED_WITH_SST (0x00FFFFFF).

## -remarks

## -see-also

[WWAN_SINGLE_NSSAI](ns-wwan-wwan_single_nssai.md)
