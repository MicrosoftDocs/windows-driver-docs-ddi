---
UID: NS:dispmprt._DXGK_FEATURE_INTERFACE
tech.root: display
title: DXGK_FEATURE_INTERFACE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGK_FEATURE_INTERFACE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_FEATURE_INTERFACE, *PDXGK_FEATURE_INTERFACE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_FEATURE_INTERFACE
 - PDXGK_FEATURE_INTERFACE
 - DXGK_FEATURE_INTERFACE
f1_keywords:
 - _DXGK_FEATURE_INTERFACE
 - dispmprt/_DXGK_FEATURE_INTERFACE
 - PDXGK_FEATURE_INTERFACE
 - dispmprt/PDXGK_FEATURE_INTERFACE
 - DXGK_FEATURE_INTERFACE
 - dispmprt/DXGK_FEATURE_INTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_FEATURE_INTERFACE
---

# DXGK_FEATURE_INTERFACE structure (dispmprt.h)

## -description

The **DXGK_FEATURE_INTERFACE** structure contains the port driver's interface that can be used to query it for its enabled features and their support.

## -struct-fields

### -field Size

Size of this structure, in bytes.

### -field Version

The version number of the feature interface. Version number constants are defined in *Dispmprt.h* (for example, DXGK_FEATURE_INTERFACE_VERSION_1).

### -field Context

Pointer to a private context block.

### -field InterfaceReference

Pointer to the port driver's interface reference function.

### -field InterfaceDereference

Pointer to the port driver's interface dereference function.

### -field IsFeatureEnabled

The port driver's [**DXGKCB_ISFEATUREENABLED2**](../d3dkmddi/nc-d3dkmddi-dxgkcb_isfeatureenabled2.md) function. KMD can call this function to query whether the system has enabled a feature.

### -field QueryFeatureInterface

The port driver's [**DXGKCB_QUERYFEATUREINTERFACE**](../d3dkmddi/nc-d3dkmddi-dxgkcb_queryfeatureinterface.md) function. KMD can call this function to query the OS for a feature's interface.

## -remarks

To get this interface, KMD calls *Dxgkrnl*'s [**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md) callback with [**ServiceType**](ne-dispmprt-dxgk_services.md) set to **DxgkServicesFeature**. KMD can call  **DxgkCbQueryServices** once it obtains the callback's pointer from a call to its [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md).

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DXGK_SERVICES**](ne-dispmprt-dxgk_services.md)

[**DXGKCB_ISFEATUREENABLED2**](../d3dkmddi/nc-d3dkmddi-dxgkcb_isfeatureenabled2.md)

[**DXGKCB_QUERYFEATUREINTERFACE**](../d3dkmddi/nc-d3dkmddi-dxgkcb_queryfeatureinterface.md)

[**DxgkCbQueryServices**](nc-dispmprt-dxgkcb_query_services.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)
