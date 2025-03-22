---
UID: NS:dispmprt._DXGKDDI_FEATURE_INTERFACE
tech.root: display
title: DXGKDDI_FEATURE_INTERFACE
ms.date: 04/05/2024
targetos: Windows
description: Learn more about the DXGKDDI_FEATURE_INTERFACE structure.
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
req.typenames: DXGKDDI_FEATURE_INTERFACE, *PDXGKDDI_FEATURE_INTERFACE
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
 - _DXGKDDI_FEATURE_INTERFACE
 - PDXGKDDI_FEATURE_INTERFACE
 - DXGKDDI_FEATURE_INTERFACE
f1_keywords:
 - _DXGKDDI_FEATURE_INTERFACE
 - dispmprt/_DXGKDDI_FEATURE_INTERFACE
 - PDXGKDDI_FEATURE_INTERFACE
 - dispmprt/PDXGKDDI_FEATURE_INTERFACE
 - DXGKDDI_FEATURE_INTERFACE
 - dispmprt/DXGKDDI_FEATURE_INTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKDDI_FEATURE_INTERFACE
---

# DXGKDDI_FEATURE_INTERFACE structure (dispmprt.h)

## -description

The **DXGKDDI_FEATURE_INTERFACE** structure contains the display kernel-mode miniport driver's (KMD's) interface that the port driver can call to query for KMD's feature support.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Version

The version number of this interface. Version number constants are defined in *Dispmprt.h* (for example, **DXGK_FEATURE_INTERFACE_VERSION_1**).

### -field Context

A pointer to a private context block.

### -field InterfaceReference

Pointer to a KMD-implemented interface reference function.

### -field InterfaceDereference

Pointer to a KMD-implemented interface dereference function.

### -field QueryFeatureSupport

Pointer to a KMD-implemented [**DxgkDdiQueryFeatureSupport**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryfeaturesupport.md) function to query feature support.

### -field QueryFeatureInterface

Pointer to a KMD-implemented [**DxgkDdiQueryFeatureInterface**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryfeaturesupport.md) function to query KMD's interfaces for a feature. The OS only calls these interfaces for enabled features, and always requests the interface for a version of the feature that the driver supports.

## -remarks

If the driver implements the **DXGKDDI_FEATURE_INTERFACE**, it no longer needs to call [**DxgkCbQueryFeatureSupport**](../d3dkmddi/nc-d3dkmddi-dxgkcb_queryfeaturesupport.md) to enable a feature in the port driver ahead of time. It can instead query feature support on demand using its **DXGKDDI_FEATURE_INTERFACE** interface.

For more information, see [Querying WDDM feature support and enablement](/windows-hardware/drivers/display/querying-wddm-feature-support-and-enablement).

## -see-also

[**DxgkDdiQueryFeatureSupport**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryfeaturesupport.md)

[**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md)
