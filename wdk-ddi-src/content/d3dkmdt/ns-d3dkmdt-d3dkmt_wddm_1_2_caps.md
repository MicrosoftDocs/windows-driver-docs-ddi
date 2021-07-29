---
UID: NS:d3dkmdt._D3DKMT_WDDM_1_2_CAPS
tech.root: display
title: D3DKMT_WDDM_1_2_CAPS
ms.date: 07/28/2021
targetos: Windows
description: D3DKMT_WDDM_1_2_CAPS is reserved for system use.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_WDDM_1_2_CAPS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_WDDM_1_2_CAPS
 - D3DKMT_WDDM_1_2_CAPS
f1_keywords:
 - _D3DKMT_WDDM_1_2_CAPS
 - d3dkmdt/_D3DKMT_WDDM_1_2_CAPS
 - D3DKMT_WDDM_1_2_CAPS
 - d3dkmdt/D3DKMT_WDDM_1_2_CAPS
dev_langs:
 - c++
---

## -description

Reserved for system use. Do not use.

## -struct-fields

### -field PreemptionCaps

Has preemption capabilities.

### -field SupportNonVGA

Supports non-VGA.

### -field SupportSmoothRotation

Supports smooth rotation.

### -field SupportPerEngineTDR

Supports per-engine timeout detection and recovery (TDR).

### -field SupportKernelModeCommandBuffer

Supports kernel-mode command buffer.

### -field SupportCCD

Supports Connecting and Configuring Displays (CCD).

### -field SupportSoftwareDeviceBitmaps

Supports software device bitmaps.

### -field SupportGammaRamp

Supports gamma ramp.

### -field SupportHWCursor

Supports hardware cursor.

### -field SupportHWVSync

Supports hardware Vsync.

### -field SupportSurpriseRemovalInHibernation

Supports surprise removal in hibernation.

### -field Reserved

Reserved.

### -field Value

An alternative way to access the cap bits.

## -remarks

The graphics kernel uses **D3DKMT_WDDM_1_2_CAPS** to store various capabilities introduced in Windows Display Driver Model (WDDM) version 1.2. The driver provides its support capabilities during initialization, so it already knows all the values specified in this structure.
