---
UID: NS:d3dkmddi._DXGKARGCB_QUERYFEATURESUPPORT
tech.root: display
title: DXGKARGCB_QUERYFEATURESUPPORT
ms.date: 09/08/2022
targetos: Windows
description: Learn more about the DXGKARGCB_QUERYFEATURESUPPORT structure.
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
req.target-min-winverclnt: Windows 10 version 20H1
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_QUERYFEATURESUPPORT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_QUERYFEATURESUPPORT
 - DXGKARGCB_QUERYFEATURESUPPORT
f1_keywords:
 - _DXGKARGCB_QUERYFEATURESUPPORT
 - d3dkmddi/_DXGKARGCB_QUERYFEATURESUPPORT
 - DXGKARGCB_QUERYFEATURESUPPORT
 - d3dkmddi/DXGKARGCB_QUERYFEATURESUPPORT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_QUERYFEATURESUPPORT
---

## -description

The **DXGKARGCB_QUERYFEATURESUPPORT** structure is the parameter passed to the [**DXGKCB_QUERYFEATURESUPPORT**](nc-d3dkmddi-dxgkcb_queryfeaturesupport.md) callback function to query for feature support.

## -struct-fields

### -field DeviceHandle

[in] Device handle that was passed to the driver [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -field FeatureId

[in] A [**DXGK_FEATURE_ID**](ne-d3dkmddi-_dxgk_feature_id.md) value that identifies the feature to query enabled state for.

### -field DriverSupportState

[in] A UINT value that indicates the driver's support state for the feature identified by **FeatureId**. This field can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| DXGK_FEATURE_SUPPORT_ALWAYS_OFF (0) | When the driver doesn’t support a feature, it shouldn’t call [**DXGKCB_QUERYFEATURESUPPORT**](nc-d3dkmddi-dxgkcb_queryfeaturesupport.md) with that feature ID. This value is provided for implementation convenience of enumerating possible driver support states for a particular feature. |
| DXGK_FEATURE_SUPPORT_EXPERIMENTAL (1) | Driver support for a feature is in the experimental state. |
| DXGK_FEATURE_SUPPORT_STABLE (2) | Driver support for a feature is in the stable state. |
| DXGK_FEATURE_SUPPORT_ALWAYS_ON (3) | Driver support for a feature is in the always-on state and the driver cannot operate without this feature enabled. |

### -field Enabled

[out] The OS sets this field to FALSE to instruct the driver not to enable the feature, and sets it to TRUE if the OS allows the driver to enable the feature.

## -see-also

[**DXGKCB_QUERYFEATURESUPPORT**](nc-d3dkmddi-dxgkcb_queryfeaturesupport.md)
