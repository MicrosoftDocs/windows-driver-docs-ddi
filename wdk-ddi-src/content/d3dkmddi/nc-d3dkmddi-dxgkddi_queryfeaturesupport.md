---
UID: NC:d3dkmddi.DXGKDDI_QUERYFEATURESUPPORT
tech.root: display
title: DXGKDDI_QUERYFEATURESUPPORT
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKDDI_QUERYFEATURESUPPORT function.
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
 - DXGKDDI_QUERYFEATURESUPPORT
f1_keywords:
 - DXGKDDI_QUERYFEATURESUPPORT
 - d3dkmddi/DXGKDDI_QUERYFEATURESUPPORT
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_QUERYFEATURESUPPORT
---

# DXGKDDI_QUERYFEATURESUPPORT function (d3dkmddi.h)

## -description

KMD's **DxgkDdiQueryFeatureSupport** function is called to query its support for a feature.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of its [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_QUERYFEATURESUPPORT**](ns-d3dkmddi-dxgkarg_queryfeaturesupport.md) structure in which input and output feature support information is stored.

## -returns

**DxgkDdiQueryFeatureSupport** returns STATUS_SUCCESS upon successful completion. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGKARG_QUERYFEATURESUPPORT**](ns-d3dkmddi-dxgkarg_queryfeaturesupport.md)

[**DXGKDDI_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgkddi_feature_interface.md)
