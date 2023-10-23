---
UID: NE:iddcx.IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
tech.root: display
title: IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS enumeration.
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
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
f1_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
 - iddcx/IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS
---

## -description

A **IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS** enumeration contains flags that indicate support for specific colorimetry and Electro-Optical Transfer Function (EOTF) capabilities.

## -enum-fields

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS_UNINITIALIZED:0x0

Indicates that an **IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS** variable has not yet been assigned a meaningful value.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS_BT2020YCC:0x1

Tells the OS that the monitor supports the BT.2020 color space using a YCC signal format.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS_BT2020RGB:0x2

Tells the OS that the monitor supports the BT.2020 color space using an RGB signal format.

### -field IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS_ST2084:0x4

ells the OS that the monitor supports the ST.2084 Electro-Optical Transfer Function (EOTF).

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY**](ns-iddcx-iddcx_displayconfig_monitor_colorimetry.md)

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
