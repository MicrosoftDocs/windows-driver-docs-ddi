---
UID: NS:d3dkmthk._D3DKMT_ISFEATUREENABLED
tech.root: display
title: D3DKMT_ISFEATUREENABLED
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the D3DKMT_ISFEATUREENABLED structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_ISFEATUREENABLED
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ISFEATUREENABLED
 - D3DKMT_ISFEATUREENABLED
f1_keywords:
 - _D3DKMT_ISFEATUREENABLED
 - d3dkmthk/_D3DKMT_ISFEATUREENABLED
 - D3DKMT_ISFEATUREENABLED
 - d3dkmthk/D3DKMT_ISFEATUREENABLED
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_ISFEATUREENABLED
---

# D3DKMT_ISFEATUREENABLED structure (d3dkmthk.h)

## -description

**D3DKMT_ISFEATUREENABLED** is a parameter for the [**D3DKMTIsFeatureEnabled**](nf-d3dkmthk-d3dkmtisfeatureenabled.md) function that queries whether a feature is enabled.

## -struct-fields

### -field hAdapter

[in] The adapter for which to query the feature. If the feature is a global feature, this value must be NULL.

### -field FeatureId

[in] A [**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md) value that specifies the feature ID to query enabled state for.

### -field Result

[out] A [**DXGK_ISFEATUREENABLED_RESULT**](../d3dukmdt/ns-d3dukmdt-dxgk_isfeatureenabled_result.md) structure that contains the result of the query.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**D3DKMTIsFeatureEnabled**](nf-d3dkmthk-d3dkmtisfeatureenabled.md)
