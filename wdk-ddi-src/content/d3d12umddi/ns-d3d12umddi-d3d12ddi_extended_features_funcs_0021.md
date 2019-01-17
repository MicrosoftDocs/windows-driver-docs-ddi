---
UID: NS:d3d12umddi.D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
title: D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
description: Specifies callback functions for extended features.
old-location: display\d3d12ddi_extended_features_funcs_0021.htm
ms.assetid: 9E2D8EF5-18D0-4BC5-ADCA-3D3BE76D3BF1
ms.date: 05/10/2018
ms.keywords: D3D12DDI_EXTENDED_FEATURES_FUNCS_0021, D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 structure [Display Devices], d3d12umddi/D3D12DDI_EXTENDED_FEATURES_FUNCS_0021, display.d3d12ddi_extended_features_funcs_0021
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
---

# D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 structure


## -description


Specifies callback functions for extended features.


## -struct-fields




### -field pfnGetSupportedExtendedFeatures

A callback function that gets supported extended features.


### -field pfnGetSupportedExtendedFeatureVersions

A callback function that gets supported versions of extended features.


### -field pfnEnableExtendedFeature

A callback function that enables an extended feature.


### -field pfnSetExtendedFeatureCallbacks

A callback function that sets extended feature callbacks function. 

