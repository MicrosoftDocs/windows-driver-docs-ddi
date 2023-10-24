---
UID: NE:iddcx.IDDCX_COLOR_SPACE
tech.root: display
title: IDDCX_COLOR_SPACE
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_COLOR_SPACE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
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
 - iddcx.h
api_name:
 - IDDCX_COLOR_SPACE
f1_keywords:
 - IDDCX_COLOR_SPACE
 - iddcx/IDDCX_COLOR_SPACE
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_COLOR_SPACE
---

## -description

An **IDDCX_COLOR_SPACE** enumeration value specifies the color space to use on the monitor.

## -enum-fields

### -field IDDCX_COLOR_SPACE_UNINITIALIZED:0

Indicates that an **IDDCX_COLOR_SPACE** variable has not yet been assigned a meaningful value.

### -field IDDCX_COLOR_SPACE_G22_P709:1

The standard definition for sRGB.

### -field IDDCX_COLOR_SPACE_G2084_P2020:2

The standard definition for HDR10.

### -field IDDCX_COLOR_SPACE_G22_P709_WCG:3

The standard definition for sRGB SDR WCG.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md)

[**IDDCX_WIRE_FORMAT_INFO**](ns-iddcx-iddcx_wire_format_info.md)
