---
UID: NS:d3dkmddi._DXGKCBINT_FEATURE_NATIVEFENCE_1
tech.root: display
title: DXGKCBINT_FEATURE_NATIVEFENCE_1
ms.date: 03/28/2024 
targetos: Windows
description: Learn more about the DXGKCBINT_FEATURE_NATIVEFENCE_1 structure.
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
req.typenames: DXGKCBINT_FEATURE_NATIVEFENCE_1
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
 - _DXGKCBINT_FEATURE_NATIVEFENCE_1
 - DXGKCBINT_FEATURE_NATIVEFENCE_1
f1_keywords:
 - _DXGKCBINT_FEATURE_NATIVEFENCE_1
 - d3dkmddi/_DXGKCBINT_FEATURE_NATIVEFENCE_1
 - DXGKCBINT_FEATURE_NATIVEFENCE_1
 - d3dkmddi/DXGKCBINT_FEATURE_NATIVEFENCE_1
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKCBINT_FEATURE_NATIVEFENCE_1
---

# DXGKCBINT_FEATURE_NATIVEFENCE_1 structure (d3dkmddi.h)

## -description

The **DXGKCBINT_FEATURE_NATIVEFENCE_1** structure is an internal driver structure used by KMD to query the OS for its support of native GPU fence features.

## -struct-fields

### -field GetOSCaps

[in/out] The OS's [**DXGKCB_FEATURE_NATIVEFENCE_CAPS_1**](nc-d3dkmddi-dxgkcb_feature_nativefence_caps_1.md) callback function from which the OS returns its support for native GPU fence features.

## -remarks

KMD queries the OS's native GPU fence features by calling the callback function that **GetOSCaps** points to. KMD should maintain an internal cache for the state and version of the results returned.

For a sample code snippet and more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKCB_FEATURE_NATIVEFENCE_CAPS_1**](nc-d3dkmddi-dxgkcb_feature_nativefence_caps_1.md)

[isfeatureenabled]()
