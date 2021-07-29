---
UID: NS:d3dkmdt._D3DKMT_WDDM_2_9_CAPS
tech.root: display
title: D3DKMT_WDDM_2_9_CAPS
ms.date: 07/28/2021
targetos: Windows
description: D3DKMT_WDDM_2_9_CAPS is reserved for system use.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: D3DKMT_WDDM_2_9_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_2_9_CAPS
 - D3DKMT_WDDM_2_9_CAPS
f1_keywords:
 - _D3DKMT_WDDM_2_9_CAPS
 - d3dkmdt/_D3DKMT_WDDM_2_9_CAPS
 - D3DKMT_WDDM_2_9_CAPS
 - d3dkmdt/D3DKMT_WDDM_2_9_CAPS
dev_langs:
 - c++
---

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field HwSchSupportState

DXGK_FEATURE_SUPPORT_*XXX* value that specifies the driver support state for GPU-supported hardware scheduling. This field can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| DXGK_FEATURE_SUPPORT_ALWAYS_OFF | When a driver doesn't support a feature, it doesn't call into QueryFeatureSupport with that feature ID. This value is provided for implementation convenience of enumerating possible driver support states for a particular feature. |
| DXGK_FEATURE_SUPPORT_EXPERIMENTAL | Driver support for a feature is in the experimental state. |
| DXGK_FEATURE_SUPPORT_STABLE       | Driver support for a feature is in the stable state.       |
| DXGK_FEATURE_SUPPORT_ALWAYS_ON    | Driver support for a feature is in the always on state. The driver doesn't operate without this feature enabled. |

### -field HwSchEnabled

Specifies whether the hardware scheduling is currently enabled for this GPU.

### -field SelfRefreshMemorySupported

Specifies whether Self Refresh Memory is supported for this GPU.

### -field Reserved

Reserved; do not use.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_2_9_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 2.9. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
