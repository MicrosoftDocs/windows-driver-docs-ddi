---
UID: NS:d3dkmddi._DXGKARGCB_QUERYFEATUREINTERFACE
tech.root: display
title: DXGKARGCB_QUERYFEATUREINTERFACE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKARGCB_QUERYFEATUREINTERFACE structure.
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
req.typenames: DXGKARGCB_QUERYFEATUREINTERFACE
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
 - _DXGKARGCB_QUERYFEATUREINTERFACE
 - DXGKARGCB_QUERYFEATUREINTERFACE
f1_keywords:
 - _DXGKARGCB_QUERYFEATUREINTERFACE
 - d3dkmddi/_DXGKARGCB_QUERYFEATUREINTERFACE
 - DXGKARGCB_QUERYFEATUREINTERFACE
 - d3dkmddi/DXGKARGCB_QUERYFEATUREINTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_QUERYFEATUREINTERFACE
---

# DXGKARGCB_QUERYFEATUREINTERFACE structure (d3dkmddi.h)

## -description

**DXGKARGCB_QUERYFEATUREINTERFACE** is the parameter to the [**DXGKCB_QUERYFEATUREINTERFACE**](nc-d3dkmddi-dxgkcb_queryfeatureinterface.md) callback function.

## -struct-fields

### -field FeatureId

[in] A [**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md) enumeration value that specifies the ID of the feature whose interface is being queried.

### -field Version

[in] The version of the feature whose interface is being queried. See Remarks.

### -field InterfaceSize

[in/out] The size of the interface buffer that **Interface** points to, in bytes. On success, this value must be set to the size of the returned interface. If the output value is less than the input size of the requested interface, the caller should return an error, such as STATUS_BUFFER_TOO_SMALL.

### -field Interface

[in/out] A pointer to the interface buffer to fill in. This buffer is guaranteed to be exactly **InterfaceSize** bytes in length.

## -remarks

Feature interfaces aren't required to be backwards compatible with older versions of the same interface. For example, the interface for version 1 and version 2 of a feature may be radically different (that is, the v2 interface doesn't need to be an extension of the v1 interface). This is useful for feature bringup when the design of a feature is iterated on over time, without the need to permanently support a DDI forever.

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_FEATURE_ID**](../d3dukmdt/ne-d3dukmdt-dxgk_feature_id.md)

[**DXGK_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgk_feature_interface.md)

[**DXGKCB_QUERYFEATUREINTERFACE**](nc-d3dkmddi-dxgkcb_queryfeatureinterface.md)
