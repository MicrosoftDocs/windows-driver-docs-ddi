---
UID: NS:d3d12umddi.D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
title: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 (d3d12umddi.h)
description: This structure contains device functions for extended features in video.
old-location: display\d3d12ddi_extended_features_funcs_0020.htm
ms.date: 05/10/2018
keywords: ["D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure"]
ms.keywords: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020, D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure [Display Devices], d3d12umddi/D3D12DDI_EXTENDED_FEATURES_FUNCS_0020, display.d3d12ddi_extended_features_funcs_0020
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
f1_keywords:
 - D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
 - d3d12umddi/D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
---

# D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure


## -description

This structure contains device functions for extended features in  video.

## -struct-fields

### -field pfnGetSupportedExtendedFeatures

A pointer for a callback function to get supported extended features.

### -field pfnGetSupportedExtendedFeatureVersions

A pointer for a callback function to get the supported versions of extended features.

### -field pfnEnableExtendedFeature

A pointer for a callback function to enable an extended feature.

