---
UID: NC:d3dkmddi.DXGKCB_ISFEATUREENABLED
title: DXGKCB_ISFEATUREENABLED
description: Queries for the enabled state of the feature.
tech.root: display
ms.date: 09/08/2022
keywords: ["DXGKCB_ISFEATUREENABLED callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903 (WDDM 2.6)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: DXGKDDI_INTERFACE_VERSION_WDDM2_6, 19H1
f1_keywords:
 - DXGKCB_ISFEATUREENABLED
 - d3dkmddi/DXGKCB_ISFEATUREENABLED
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_ISFEATUREENABLED
dev_langs:
 - c++
---

# DXGKCB_ISFEATUREENABLED callback function

## -description

A kernel-mode display miniport driver (KMD) calls **DXGKCB_ISFEATUREENABLED** to query whether the OS will permit it to enable support for a feature.

## -parameters

### -param unnamedParam1 [in/out]

Pointer to a [**DXGKARGCB_ISFEATUREENABLED**](ns-d3dkmddi-_dxgkargcb_isfeatureenabled.md) structure that contains information about the feature being queried.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

Starting in WDDM 2.9, drivers can call [**DXGKCB_QUERYFEATURESUPPORT**](nc-d3dkmddi-dxgkcb_queryfeaturesupport.md) to provide additional information to the OS.

The OS sets the **Enabled** member of [**DXGKARGCB_ISFEATUREENABLED**](ns-d3dkmddi-_dxgkargcb_isfeatureenabled.md) to TRUE when it allows the driver to enable support for the queried feature. **Enabled** is set to FALSE to instruct the driver to not enable its support for the feature.

**DXGKCB_*XXX*** functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_ISFEATUREENABLED**](ns-d3dkmddi-_dxgkargcb_isfeatureenabled.md) and then call **DxgkCbIsFeatureEnabled** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_ISFEATUREENABLED**](ns-d3dkmddi-_dxgkargcb_isfeatureenabled.md)

[**DXGKCB_QUERYFEATURESUPPORT**](nc-d3dkmddi-dxgkcb_queryfeaturesupport.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
