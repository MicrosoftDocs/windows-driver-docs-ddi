---
UID: NS:d3dkmdt._D3DKMT_WDDM_3_0_CAPS
tech.root: display
title: D3DKMT_WDDM_3_0_CAPS
ms.date: 07/28/2021
targetos: Windows
description: D3DKMT_WDDM_3_0_CAPS is reserved for system use.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_WDDM_3_0_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_3_0_CAPS
 - D3DKMT_WDDM_3_0_CAPS
f1_keywords:
 - _D3DKMT_WDDM_3_0_CAPS
 - d3dkmdt/_D3DKMT_WDDM_3_0_CAPS
 - D3DKMT_WDDM_3_0_CAPS
 - d3dkmdt/D3DKMT_WDDM_3_0_CAPS
dev_langs:
 - c++
---

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field HwFlipQueueSupportState

DXGK_FEATURE_SUPPORT_*XXX* value that specifies the driver support state for GPU-supported hardware flip queue. This field can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| DXGK_FEATURE_SUPPORT_ALWAYS_OFF | When a driver doesn't support a feature, it doesn't call into QueryFeatureSupport with that feature ID. This value is provided for implementation convenience of enumerating possible driver support states for a particular feature. |
| DXGK_FEATURE_SUPPORT_EXPERIMENTAL | Driver support for a feature is in the experimental state. |
| DXGK_FEATURE_SUPPORT_STABLE       | Driver support for a feature is in the stable state.       |
| DXGK_FEATURE_SUPPORT_ALWAYS_ON    | Driver support for a feature is in the always on state. The driver doesn't operate without this feature enabled. |

### -field HwFlipQueueEnabled

Specifies whether the hardware flip queue is currently enabled for this GPU.

### -field DisplayableSupported

Specifies whether displayable feature is supported.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_3_0_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 3.0. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
