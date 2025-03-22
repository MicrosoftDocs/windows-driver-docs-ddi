---
UID: NS:d3dkmdt._D3DKMT_WDDM_3_1_CAPS
tech.root: display
title: D3DKMT_WDDM_3_1_CAPS
ms.date: 03/21/2024
targetos: Windows
description: Learn about the D3DKMT_WDDM_3_1_CAPS structure.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_WDDM_3_1_CAPS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_3_1_CAPS
 - D3DKMT_WDDM_3_1_CAPS
f1_keywords:
 - _D3DKMT_WDDM_3_1_CAPS
 - d3dkmdt/_D3DKMT_WDDM_3_1_CAPS
 - D3DKMT_WDDM_3_1_CAPS
 - d3dkmdt/D3DKMT_WDDM_3_1_CAPS
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_WDDM_3_1_CAPS
---

# D3DKMT_WDDM_3_1_CAPS structure (d3dkmdt.h)

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field NativeGpuFenceSupported

Specifies whether the native GPU fence feature is supported by this GPU. For more information about the native GPU fence feature, see [Native GPU fence](/windows-hardware/drivers/display/native-gpu-fence-objects).

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_3_1_CAPS** to store various capabilities introduced in WDDM version 3.1. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
