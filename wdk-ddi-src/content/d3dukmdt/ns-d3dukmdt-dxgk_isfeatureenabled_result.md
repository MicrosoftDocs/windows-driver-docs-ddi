---
UID: NS:d3dukmdt._DXGK_ISFEATUREENABLED_RESULT
tech.root: display
title: DXGK_ISFEATUREENABLED_RESULT
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGK_ISFEATUREENABLED_RESULT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_ISFEATUREENABLED_RESULT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _DXGK_ISFEATUREENABLED_RESULT
 - DXGK_ISFEATUREENABLED_RESULT
f1_keywords:
 - _DXGK_ISFEATUREENABLED_RESULT
 - d3dukmdt/_DXGK_ISFEATUREENABLED_RESULT
 - DXGK_ISFEATUREENABLED_RESULT
 - d3dukmdt/DXGK_ISFEATUREENABLED_RESULT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_ISFEATUREENABLED_RESULT
---

# DXGK_ISFEATUREENABLED_RESULT structure (d3dukmdt.h)

## -description

The **DXGK_ISFEATUREENABLED_RESULT** structure defines the results of a feature query.

## -struct-fields

### -field Version

When enabled (**Enabled**=TRUE), **Version** is the negotiated version of the feature that is used. This value is the highest version that is supported by both the OS and driver. For example, if the OS supports versions 1 through 3, and the driver supports versions 2 through 5, the resulting negotiated feature version is 3.

### -field Enabled

When set, the feature is enabled.

### -field KnownFeature

When set, the feature is known to the OS.

### -field SupportedByDriver

When set, the feature is supported by the driver. **SupportedByDriver** is set only if the feature depends on the driver support.

### -field SupportedOnCurrentConfig

When set, the feature is supported on the current configuration.

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the bit fields of this structure.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**D3DKMT_ISFEATUREENABLED**](../d3dkmthk/ns-d3dkmthk-d3dkmt_isfeatureenabled.md)

[**DXGK_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgk_feature_interface.md)

[**DXGK_FEATURE_INTERFACE:IsFeatureEnabled**](../d3dkmddi/nf-d3dkmddi-dxgkisfeatureenabled2.md)
