---
UID: NE:iddcx.IDDCX_FEATURE_IMPLEMENTATION
title: IDDCX_FEATURE_IMPLEMENTATION (iddcx.h)
description: Enum used to indicate how a given supported feature is implemented.
old-location: display\iddcx_feature_implementation.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_FEATURE_IMPLEMENTATION enumeration"]
ms.keywords: IDDCX_FEATURE_IMPLEMENTATION, IDDCX_FEATURE_IMPLEMENTATION enumeration [Display Devices], IDDCX_FEATURE_IMPLEMENTATION_HARDWARE, IDDCX_FEATURE_IMPLEMENTATION_NONE, IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE, IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED, display.iddcx_feature_implementation, iddcx/IDDCX_FEATURE_IMPLEMENTATION, iddcx/IDDCX_FEATURE_IMPLEMENTATION_HARDWARE, iddcx/IDDCX_FEATURE_IMPLEMENTATION_NONE, iddcx/IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE, iddcx/IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED
req.header: iddcx.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - IDDCX_FEATURE_IMPLEMENTATION
 - iddcx/IDDCX_FEATURE_IMPLEMENTATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_FEATURE_IMPLEMENTATION
---

# IDDCX_FEATURE_IMPLEMENTATION enumeration

## -description

A **IDDCX_FEATURE_IMPLEMENTATION** value is used to indicate how a given supported feature is implemented.

## -enum-fields

### -field IDDCX_FEATURE_IMPLEMENTATION_UNINITIALIZED:0

Indicates that an **IDDCX_FEATURE_IMPLEMENTATION** variable has not yet been assigned a meaningful value.

### -field IDDCX_FEATURE_IMPLEMENTATION_NONE:1

The feature is not implemented.

### -field IDDCX_FEATURE_IMPLEMENTATION_HARDWARE:2

The feature is implemented and hardware is used in the implementation. For example, the adapter display pipeline blends the hardware cursor image into the signal sent to the monitor.

### -field IDDCX_FEATURE_IMPLEMENTATION_SOFTWARE:3

The feature is implemented and software is used in the implementation. For example, the driver supports hardware cursor by blending the cursor image into the display pixels as part of the processing.

## -see-also

[**IDDCX_ENDPOINT_DIAGNOSTIC_INFO**](ns-iddcx-iddcx_endpoint_diagnostic_info.md)
