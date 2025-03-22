---
UID: NF:d3dkmddi.DxgkIsFeatureEnabled2
tech.root: display
title: DxgkIsFeatureEnabled2
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DxgkIsFeatureEnabled2 function.
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
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DxgkIsFeatureEnabled2
f1_keywords:
 - DxgkIsFeatureEnabled2
 - d3dkmddi/DxgkIsFeatureEnabled2
dev_langs:
 - c++
helpviewer_keywords:
 - DxgkIsFeatureEnabled2
---

# DxgkIsFeatureEnabled2 function (d3dkmddi.h)

## -description

KMD can call the display port driver's **DxgkIsFeatureEnabled2** function before *Dxgkrnl* is enabled to determine whether a particular feature is enabled.

## -parameters

### -param DriverObject

[in] Pointer to a [DRIVER_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object). The display miniport driver previously obtained this pointer in its [**DriverEntry**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver) function.

### -param pArgs

[in] Pointer to a [**DXGKARGCB_ISFEATUREENABLED2**](ns-d3dkmddi-dxgkargcb_isfeatureenabled2.md) structure that contains information about the feature to query.

## -returns

**DxgkIsFeatureEnabled2** returns STATUS_SUCCESS upon success completion. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

**DxgkIsFeatureEnabled2** is defined in the display port driver's library (*displib.lib*). As a result, KMD can call this function to check for the presence of an enabled feature before *Dxgkrnl* is initialized. Because **DxgkIsFeatureEnabled2** is intended to be used at [**DriverEntry**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver), only a subset of global features can be queried through it. This subset currently includes:

* DXGK_FEATURE_GPUVAIOMMU

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DriverEntry**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver)

[**DXGKARGCB_ISFEATUREENABLED2**](ns-d3dkmddi-dxgkargcb_isfeatureenabled2.md)
