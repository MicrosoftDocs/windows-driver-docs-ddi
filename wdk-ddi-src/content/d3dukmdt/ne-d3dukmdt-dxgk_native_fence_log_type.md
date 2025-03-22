---
UID: NE:d3dukmdt._DXGK_NATIVE_FENCE_LOG_TYPE
tech.root: display
title: DXGK_NATIVE_FENCE_LOG_TYPE
ms.date: 03/21/2024
targetos: Windows
description: Learn more about the DXGK_NATIVE_FENCE_LOG_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _DXGK_NATIVE_FENCE_LOG_TYPE
 - DXGK_NATIVE_FENCE_LOG_TYPE
f1_keywords:
 - _DXGK_NATIVE_FENCE_LOG_TYPE
 - d3dukmdt/_DXGK_NATIVE_FENCE_LOG_TYPE
 - DXGK_NATIVE_FENCE_LOG_TYPE
 - d3dukmdt/DXGK_NATIVE_FENCE_LOG_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_NATIVE_FENCE_LOG_TYPE
---

# DXGK_NATIVE_FENCE_LOG_TYPE enumeration (d3dukmdt.h)

## -description

A **DXGK_NATIVE_FENCE_LOG_TYPE** value identifies the type of a native log entry.

## -enum-fields

### -field DXGK_NATIVE_FENCE_LOG_TYPE_WAITS:1

The log entry is for a wait.

### -field DXGK_NATIVE_FENCE_LOG_TYPE_SIGNALS:2

The log entry is for a signal.

## -remarks

For more information about native GPU fences and log buffer usage, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGK_NATIVE_FENCE_LOG_HEADER**](ns-d3dukmdt-dxgk_native_fence_log_header.md)

[**DxgkDdiSetNativeFenceLogBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setnativefencelogbuffer.md)
