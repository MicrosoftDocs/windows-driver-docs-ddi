---
UID: NS:d3dkmdt._D3DKMT_WDDM_1_3_CAPS
title: D3DKMT_WDDM_1_3_CAPS (d3dkmdt.h)
description: D3DKMT_WDDM_1_3_CAPS is reserved for system use.
ms.date: 07/28/2021
keywords: ["D3DKMT_WDDM_1_3_CAPS structure"]
ms.keywords: _D3DKMT_WDDM_1_3_CAPS, D3DKMT_WDDM_1_3_CAPS,
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_WDDM_1_3_CAPS
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_WDDM_1_3_CAPS
 - d3dkmdt/_D3DKMT_WDDM_1_3_CAPS
 - D3DKMT_WDDM_1_3_CAPS
 - d3dkmdt/D3DKMT_WDDM_1_3_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_1_3_CAPS
 - D3DKMT_WDDM_1_3_CAPS
---

# D3DKMT_WDDM_1_3_CAPS structure

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field SupportMiracast

Supports Miracast.

### -field IsHybridIntegratedGPU

The display is hybrid integrated GPU.

### -field IsHybridDiscreteGPU

The display is hybrid discrete GPU.

### -field SupportPowerManagementPStates

Supports power management states.

### -field SupportVirtualModes

Supports virtual modes.

### -field SupportCrossAdapterResource

Supports cross adapter resource.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_1_3_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 1.3. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
