---
UID: NS:d3dkmdt._D3DKMT_WDDM_2_0_CAPS
title: D3DKMT_WDDM_2_0_CAPS (d3dkmdt.h)
description: D3DKMT_WDDM_2_0_CAPS is reserved for system use.
ms.date: 07/28/2021
keywords: ["D3DKMT_WDDM_2_0_CAPS structure"]
ms.keywords: _D3DKMT_WDDM_2_0_CAPS, D3DKMT_WDDM_2_0_CAPS,
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_WDDM_2_0_CAPS
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_WDDM_2_0_CAPS
 - d3dkmdt/_D3DKMT_WDDM_2_0_CAPS
 - D3DKMT_WDDM_2_0_CAPS
 - d3dkmdt/D3DKMT_WDDM_2_0_CAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_2_0_CAPS
 - D3DKMT_WDDM_2_0_CAPS
---

# D3DKMT_WDDM_2_0_CAPS structure

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field Support64BitAtomics

Supports 64-bit atomics.

### -field GpuMmuSupported

Supports GPU memory management.

### -field IoMmuSupported

Supports input/output memory management.

### -field FlipOverwriteSupported

Supports flip overwrite.

### -field SupportContextlessPresent

Supports contextless present display.

### -field SupportSurpriseRemoval

Supports surprise removal.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_2_0_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 2.0. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
