---
UID: NS:d3dkmddi._DXGKARGCB_ISFEATUREENABLED2
tech.root: display
title: DXGKARGCB_ISFEATUREENABLED2
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKARGCB_ISFEATUREENABLED2 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARGCB_ISFEATUREENABLED2
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
 - _DXGKARGCB_ISFEATUREENABLED2
 - DXGKARGCB_ISFEATUREENABLED2
f1_keywords:
 - _DXGKARGCB_ISFEATUREENABLED2
 - d3dkmddi/_DXGKARGCB_ISFEATUREENABLED2
 - DXGKARGCB_ISFEATUREENABLED2
 - d3dkmddi/DXGKARGCB_ISFEATUREENABLED2
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_ISFEATUREENABLED2
---

# DXGKARGCB_ISFEATUREENABLED2 structure (d3dkmddi.h)

## -description

The **DXGKARGCB_ISFEATUREENABLED2** structure is the parameter for the [**DXGKCB_ISFEATUREENABLED2**](nc-d3dkmddi-dxgkcb_isfeatureenabled2.md) callback function.

## -struct-fields

### -field FeatureId

[in] A [**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md) value that identifies the feature to query enabled state for.

### -field Flags

[in] A [**DXGKARGCB_ISFEATUREENABLED2_FLAGS**](ns-d3dkmddi-dxgkargcb_isfeatureenabled2_flags.md) value that specifies optional feature query flags.

### -field Result

[out] A [**DXGK_ISFEATUREENABLED_RESULT**](../d3dukmdt/ns-d3dukmdt-dxgk_isfeatureenabled_result.md) value in which the result of the feature query is returned.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGKCB_ISFEATUREENABLED2**](nc-d3dkmddi-dxgkcb_isfeatureenabled2.md)
