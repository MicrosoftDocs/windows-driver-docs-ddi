---
UID: NC:d3dkmddi.DXGKCB_QUERYFEATUREINTERFACE
tech.root: display
title: DXGKCB_QUERYFEATUREINTERFACE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKCB_QUERYFEATUREINTERFACE callback function.
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
 - DXGKCB_QUERYFEATUREINTERFACE
f1_keywords:
 - DXGKCB_QUERYFEATUREINTERFACE
 - d3dkmddi/DXGKCB_QUERYFEATUREINTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKCB_QUERYFEATUREINTERFACE
---

# DXGKCB_QUERYFEATUREINTERFACE function (d3dkmddi.h)

## -description

**DXGKCB_QUERYFEATUREINTERFACE** is a port driver-implemented callback function that is used to query for a feature interface.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of its [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARGCB_QUERYFEATUREINTERFACE**](ns-d3dkmddi-dxgkarg_queryfeatureinterface.md) structure in which input and output information about the port driver's feature's interface is stored.

## -returns

**DXGKCB_QUERYFEATUREINTERFACE** returns STATUS_SUCCESS upon successful completion. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_FEATURE_INTERFACE**](../dispmprt/ns-dispmprt-dxgk_feature_interface.md)

[**DXGKARGCB_QUERYFEATUREINTERFACE**](ns-d3dkmddi-dxgkarg_queryfeatureinterface.md)
