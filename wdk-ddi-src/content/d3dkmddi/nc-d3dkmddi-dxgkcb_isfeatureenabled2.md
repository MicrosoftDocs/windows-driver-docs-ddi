---
UID: NC:d3dkmddi.DXGKCB_ISFEATUREENABLED2
tech.root: display
title: DXGKCB_ISFEATUREENABLED2
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKCB_ISFEATUREENABLED2 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ISFEATUREENABLED2
f1_keywords:
 - DXGKCB_ISFEATUREENABLED2
 - d3dkmddi/DXGKCB_ISFEATUREENABLED2
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKCB_ISFEATUREENABLED2
---

## -description

A kernel-mode display miniport driver (KMD) calls **DXGKCB_ISFEATUREENABLED2** to query whether the OS has enabled a feature.

## -parameters

### -param hAdapter

[in] The adapter for which to query the feature. If the feature is a global feature, this value must be NULL.

### -param pArgs

[in/out] Pointer to a [**DXGKARGCB_ISFEATUREENABLED2**](ns-d3dkmddi-dxgkargcb_isfeatureenabled2.md) structure that contains information about the feature being queried.

## -returns

**DXGKCB_ISFEATUREENABLED2** returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS code.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgk_feature_interface.md)

[**DXGKARGCB_ISFEATUREENABLED2**](ns-d3dkmddi-dxgkargcb_isfeatureenabled2.md)
