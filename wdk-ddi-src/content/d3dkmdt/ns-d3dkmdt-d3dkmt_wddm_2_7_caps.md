---
UID: NS:d3dkmdt._D3DKMT_WDDM_2_7_CAPS
tech.root: display
title: D3DKMT_WDDM_2_7_CAPS
ms.date: 07/28/2021
targetos: Windows
description: D3DKMT_WDDM_2_7_CAPS is reserved for system use.
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
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_WDDM_2_7_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_2_7_CAPS
 - D3DKMT_WDDM_2_7_CAPS
f1_keywords:
 - _D3DKMT_WDDM_2_7_CAPS
 - d3dkmdt/_D3DKMT_WDDM_2_7_CAPS
 - D3DKMT_WDDM_2_7_CAPS
 - d3dkmdt/D3DKMT_WDDM_2_7_CAPS
dev_langs:
 - c++
---

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field HwSchSupported

Supports hardware-accelerated GPU scheduling.

### -field HwSchEnabled

Indicates that hardware-accelerated GPU scheduling is enabled.

### -field HwSchEnabledByDefault

Indicates that hardware-accelerated GPU scheduling is enabled by default.

### -field IndependentVidPnVSyncControl

The driver supports independent VidPn VSync control.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_2_7_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 2.7. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
