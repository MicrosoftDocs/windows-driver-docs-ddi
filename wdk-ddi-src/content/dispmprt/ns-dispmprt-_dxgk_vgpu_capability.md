---
UID: NS:dispmprt._DXGK_VGPU_CAPABILITY
title: _DXGK_VGPU_CAPABILITY
description: Contains info about a virtual GPU capability.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGK_VGPU_CAPABILITY structure"]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VGPU_CAPABILITY, DXGK_VGPU_CAPABILITY, *PDXGK_VGPU_CAPABILITY,
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_VGPU_CAPABILITY, *PDXGK_VGPU_CAPABILITY
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _DXGK_VGPU_CAPABILITY
 - dispmprt/_DXGK_VGPU_CAPABILITY
 - PDXGK_VGPU_CAPABILITY
 - dispmprt/PDXGK_VGPU_CAPABILITY
 - DXGK_VGPU_CAPABILITY
 - dispmprt/DXGK_VGPU_CAPABILITY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_VGPU_CAPABILITY
 - PDXGK_VGPU_CAPABILITY
 - DXGK_VGPU_CAPABILITY
product:
 - Windows
dev_langs:
 - c++
---

# _DXGK_VGPU_CAPABILITY structure


## -description

Contains info about a virtual GPU capability.

## -struct-fields

### -field MinValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field MaxValue

When the vGPU is running, each capability cannot be lower than *MinValue* and more than *MaxValue*.

### -field CurrentValue

## -remarks

## -see-also

