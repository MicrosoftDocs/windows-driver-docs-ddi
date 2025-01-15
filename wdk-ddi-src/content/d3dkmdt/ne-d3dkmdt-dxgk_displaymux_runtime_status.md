---
UID: NE:d3dkmdt._DXGK_DISPLAYMUX_RUNTIME_STATUS
tech.root: display
title: DXGK_DISPLAYMUX_RUNTIME_STATUS
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGK_DISPLAYMUX_RUNTIME_STATUS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
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
 - d3dkmdt.h
api_name:
 - _DXGK_DISPLAYMUX_RUNTIME_STATUS
 - PDXGK_DISPLAYMUX_RUNTIME_STATUS
 - DXGK_DISPLAYMUX_RUNTIME_STATUS
f1_keywords:
 - _DXGK_DISPLAYMUX_RUNTIME_STATUS
 - d3dkmdt/_DXGK_DISPLAYMUX_RUNTIME_STATUS
 - PDXGK_DISPLAYMUX_RUNTIME_STATUS
 - d3dkmdt/PDXGK_DISPLAYMUX_RUNTIME_STATUS
 - DXGK_DISPLAYMUX_RUNTIME_STATUS
 - d3dkmdt/DXGK_DISPLAYMUX_RUNTIME_STATUS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_DISPLAYMUX_RUNTIME_STATUS
---

## -description

The **DXGK_DISPLAYMUX_RUNTIME_STATUS** enumeration specifies the runtime status level of automatic display switch (ADS) support that the driver provides.

## -enum-fields

### -field DXGK_DISPLAYMUX_RUNTIME_STATUS_UNINITIALIZED:0

A variable of this enumeration type hasn't yet been assigned a meaningful value.

### -field DXGK_DISPLAYMUX_RUNTIME_STATUS_OK:1

The GPU supports ADS and the driver has obtained required information from the system.

### -field DXGK_DISPLAYMUX_RUNTIME_STATUS_NO_GPU_SUPPORT:2

The GPU doesn't support ADS.

### -field DXGK_DISPLAYMUX_RUNTIME_STATUS_NON_CRITICAL_SYSTEM_INFO_MISSING:3

The driver couldn't obtain some non-critical information from the system. ADS can still function but the user's experience might be impacted.

### -field DXGK_DISPLAYMUX_RUNTIME_STATUS_CRITICAL_SYSTEM_INFO_MISSING:4

The driver couldn't obtain some critical information from the system. ADS can still function but the user's experience might be impacted.

## -remarks

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkDdiDisplayMuxGetRuntimeStatus**](../dispmprt/nc-dispmprt-dxgkddi_displaymux_get_runtime_status.md)
