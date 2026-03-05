---
UID: NS:iddcx.IDARG_OUT_FEATURES_SUPPORTED
title: IDARG_OUT_FEATURES_SUPPORTED (iddcx.h)
description: Contains the IddCx 1.11 features that were requested.
prerelease: true
old-location:
tech.root: display
ms.date: 02/17/2026
keywords: ["IDARG_OUT_FEATURES_SUPPORTED structure"]
ms.keywords: IDARG_OUT_FEATURES_SUPPORTED, IDARG_OUT_FEATURES_SUPPORTED structure [Display Devices], display.idarg_out_features_supported, iddcx/IDARG_OUT_FEATURES_SUPPORTED
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
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
req.typenames: 
f1_keywords:
 - IDARG_OUT_FEATURES_SUPPORTED
 - iddcx/IDARG_OUT_FEATURES_SUPPORTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_FEATURES_SUPPORTED
---

# IDARG_OUT_FEATURES_SUPPORTED structure

## -description

Contains the IddCx 1.11 features that were requested.

## -struct-fields

### -field Size

[out] The total size of the structure.

### -field Features_1_11

[out] An [IDDCX_DEVICE_FEATURES_1_11](ne-iddcx-iddcx_device_features_1_11.md) enumeration indicating the IddCx 1.11 features supported by the OS.

## -see-also

[IddCxCheckOsFeatureSupport](nf-iddcx-iddcxcheckosfeaturesupport.md)
