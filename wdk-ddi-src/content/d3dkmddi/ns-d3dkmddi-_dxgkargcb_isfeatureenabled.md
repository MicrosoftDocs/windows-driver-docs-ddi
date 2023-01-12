---
UID: NS:d3dkmddi._DXGKARGCB_ISFEATUREENABLED
title: DXGKARGCB_ISFEATUREENABLED
description: Learn more about the DXGKARGCB_ISFEATUREENABLED structure.
tech.root: display
ms.date: 09/08/2022
keywords: ["DXGKARGCB_ISFEATUREENABLED structure"]
ms.keywords: _DXGKARGCB_ISFEATUREENABLED, DXGKARGCB_ISFEATUREENABLED, *INOUT_PDXGKARGCB_ISFEATUREENABLED
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903 (WDDM 2.6)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_ISFEATUREENABLED
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - _DXGKARGCB_ISFEATUREENABLED
 - d3dkmddi/_DXGKARGCB_ISFEATUREENABLED
 - DXGKARGCB_ISFEATUREENABLED
 - d3dkmddi/DXGKARGCB_ISFEATUREENABLED
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_ISFEATUREENABLED
 - DXGKARGCB_ISFEATUREENABLED
product:
 - Windows
dev_langs:
 - c++
---

# DXGKARGCB_ISFEATUREENABLED structure

## -description

The **DXGKARGCB_ISFEATUREENABLED** structure contains the arguments used in the [**DXGKCB_ISFEATUREENABLED**](nc-d3dkmddi-dxgkcb_isfeatureenabled.md) callback function, to query a driver feature's enabled state.

## -struct-fields

### -field DeviceHandle [in]

Device handle that was passed to the driver's [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -field FeatureId [in]

A [**DXGK_FEATURE_ID**](ne-d3dkmddi-_dxgk_feature_id.md) value that identifies the feature to query enabled state for.

### -field Enabled [out]

FALSE if the OS instructs the driver not to enable the feature. TRUE if the OS allows the driver to enable the feature.

## -see-also

[**DXGKCB_ISFEATUREENABLED**](nc-d3dkmddi-dxgkcb_isfeatureenabled.md)
