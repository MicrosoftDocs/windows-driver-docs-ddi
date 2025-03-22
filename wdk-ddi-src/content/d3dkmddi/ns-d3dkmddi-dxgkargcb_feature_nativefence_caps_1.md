---
UID: NS:d3dkmddi._DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
tech.root: display
title: DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
 - DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
f1_keywords:
 - _DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
 - d3dkmddi/_DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
 - DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
 - d3dkmddi/DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1
---

# DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1 structure (d3dkmddi.h)

## -description

The **DXGKARGCB_FEATURE_NATIVEFENCE_CAPS_1** structure describes the native fence capabilities of the OS.

## -struct-fields

### -field SupportOptimizedDefaultFenceType

Indicates whether the OS supports **D3DDDI_NATIVEFENCE_TYPE_DEFAULT** as described in [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). If the OS sets this as TRUE, the OS supports allocating native fence storage in VRAM. KMD should query this OS cap and determine whether the OS allows KMD to specify a local memory **SupportedSegmentSet** during the creation of fence type **D3DDDI_NATIVEFENCE_TYPE_DEFAULT**.

### -field SupportIntraGpuFenceType

Indicates whether the OS supports **D3DDDI_NATIVEFENCE_TYPE_INTRA_GPU** as described in [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -remarks

For a sample code snippet and more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKCB_FEATURE_NATIVEFENCE_CAPS_1**](nc-d3dkmddi-dxgkcb_feature_nativefence_caps_1.md)
