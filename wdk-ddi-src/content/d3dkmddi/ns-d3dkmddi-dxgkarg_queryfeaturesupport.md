---
UID: NS:d3dkmddi._DXGKARG_QUERYFEATURESUPPORT
tech.root: display
title: DXGKARG_QUERYFEATURESUPPORT
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKARG_QUERYFEATURESUPPORT structure.
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
req.typenames: DXGKARG_QUERYFEATURESUPPORT
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
 - _DXGKARG_QUERYFEATURESUPPORT
 - DXGKARG_QUERYFEATURESUPPORT
f1_keywords:
 - _DXGKARG_QUERYFEATURESUPPORT
 - d3dkmddi/_DXGKARG_QUERYFEATURESUPPORT
 - DXGKARG_QUERYFEATURESUPPORT
 - d3dkmddi/DXGKARG_QUERYFEATURESUPPORT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_QUERYFEATURESUPPORT
---

# DXGKARG_QUERYFEATURESUPPORT structure (d3dkmddi.h)

## -description

**DXGKARG_QUERYFEATURESUPPORT** is the parameter to the [**DxgkDdiQueryFeatureSupport**](nc-d3dkmddi-dxgkddi_queryfeaturesupport.md) function.

## -struct-fields

### -field FeatureId

[in] A [**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md) value that specifies the ID of the feature being queried.

### -field MinSupportedVersion

[out] Driver-defined value that identifies the minimum version supported by the driver. If **SupportedByDriver** is TRUE, this value must be non-zero.

### -field MaxSupportedVersion

[out] Driver-defined value that identifies the maximum version supported by the driver. If **SupportedByDriver** is TRUE, this value must be non-zero, and must be greater than or equal to **MinSupportedVersion**.

### -field AllowExperimental

[in] If TRUE, the driver may report experimental features as supported. If FALSE, the driver must report an experimental feature as unsupported. The OS determines whether a particular feature is allowed to be enabled in an experimental state or not. See Remarks.

### -field SupportedByDriver

[out] The driver sets this to TRUE if it implements and supports this feature; otherwise, it sets it to FALSE. See Remarks.

### -field SupportedOnCurrentConfig

[out] The driver sets this to TRUE if the current configuration supports this feature; otherwise, it sets it to FALSE.

## -remarks

The distinction between **SupportedByDriver** and **SupportedOnCurrentConfig** is used to determine if the system is capable of actually using a particular feature. For example, in a test environment, it's often important to understand that the driver supports a feature, but is running on older hardware that doesn't support it. Such a test should be skipped instead of reporting a failure. For a feature to be considered enabled, both values must be reported as TRUE by the driver.

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md)

[**DXGKDDI_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgkddi_feature_interface.md)

[**DxgkDdiQueryFeatureSupport**](nc-d3dkmddi-dxgkddi_queryfeaturesupport.md)
