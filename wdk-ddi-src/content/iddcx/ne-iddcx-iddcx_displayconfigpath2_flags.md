---
UID: NE:iddcx.IDDCX_DISPLAYCONFIGPATH2_FLAGS
tech.root: display
title: IDDCX_DISPLAYCONFIGPATH2_FLAGS
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIGPATH2_FLAGS enumeration.
prerelease: true
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
 - IDDCX_DISPLAYCONFIGPATH2_FLAGS
f1_keywords:
 - IDDCX_DISPLAYCONFIGPATH2_FLAGS
 - iddcx/IDDCX_DISPLAYCONFIGPATH2_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIGPATH2_FLAGS
---

## -description

An **IDDCX_DISPLAYCONFIGPATH2_FLAGS** enumeration value identifies the flags for the path, including which fields in the [**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md) structure contain valid data.

## -enum-fields

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_UNINITIALIZED:0x0

Indicates that an **IDDCX_DISPLAYCONFIGPATH2_FLAGS** variable has not yet been assigned a meaningful value.

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_MODE_VALID:0x1

If set, the accompanying [**IDDCX_DISPLAYCONFIGPATH2::Mode**](ns-iddcx-iddcx_displayconfigpath2.md) field contains valid data.

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SCALE_FACTOR_VALID:0x2

If set, the accompanying [**IDDCX_DISPLAYCONFIGPATH2::MonitorScaleFactor**](ns-iddcx-iddcx_displayconfigpath2.md) field contains valid data.

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_PHYSICAL_SIZE_VALID:0x4

If set, the accompanying [**IDDCX_DISPLAYCONFIGPATH2::MonitorPhysicalSize**](ns-iddcx-iddcx_displayconfigpath2.md) field contains valid data.

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_COLORIMETRY_VALID:0x8

If set, the accompanying [**IDDCX_DISPLAYCONFIGPATH2::MonitorColorimetry**](ns-iddcx-iddcx_displayconfigpath2.md) field contains valid data.

### -field IDDCX_DISPLAYCONFIGPATH2_FLAGS_MONITOR_SDRWHITELEVEL_VALID:0x10

If set, the accompanying [**IDDCX_DISPLAYCONFIGPATH2::MonitorSdrWhiteLevel**](ns-iddcx-iddcx_displayconfigpath2.md) field contains valid data.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
