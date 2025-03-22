---
UID: NC:d3dkmddi.DXGKDDI_QUERYFEATUREINTERFACE
tech.root: display
title: DXGKDDI_QUERYFEATUREINTERFACE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKDDI_QUERYFEATUREINTERFACE function.
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
 - DXGKDDI_QUERYFEATUREINTERFACE
f1_keywords:
 - DXGKDDI_QUERYFEATUREINTERFACE
 - d3dkmddi/DXGKDDI_QUERYFEATUREINTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_QUERYFEATUREINTERFACE
---

# DXGKDDI_QUERYFEATUREINTERFACE function (d3dkmddi.h)

## -description

KMD's **DxgkDdiQueryFeatureInterface** function is called to query its interface for a feature.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of its [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_QUERYFEATUREINTERFACE**](ns-d3dkmddi-dxgkarg_queryfeatureinterface.md) structure in which input and output information about the feature's interface is stored.

## -returns

**DxgkDdiQueryFeatureInterface** returns STATUS_SUCCESS upon successful completion. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGKARG_QUERYFEATUREINTERFACE**](ns-d3dkmddi-dxgkarg_queryfeatureinterface.md)

[**DXGKDDI_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgkddi_feature_interface.md)
