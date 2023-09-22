---
UID: NS:iddcx.IDDCX_DISPLAYCONFIG_MODE
tech.root: display
title: IDDCX_DISPLAYCONFIG_MODE
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIG_MODE structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_DISPLAYCONFIG_MODE
f1_keywords:
 - IDDCX_DISPLAYCONFIG_MODE
 - iddcx/IDDCX_DISPLAYCONFIG_MODE
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIG_MODE
---

## -description

The **IDDCX_DISPLAYCONFIG_MODE** structure contains details of the mode to be set for the monitor in a path.

## -struct-fields

### -field Position

A [**POINT**](/windows/win32/api/windef/ns-windef-point) structure that contains the requested desktop position for this path.

### -field Resolution

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains the resolution for this path. **Resolution** must match a resolution supported by the driver.

### -field Rotation

A [**DISPLAYCONFIG_ROTATION**](/windows/win32/api/wingdi/ne-wingdi-displayconfig_rotation) value that specifies the requested screen orientation for this path.

### -field RefreshRate

A [**DISPLAYCONFIG_RATIONAL**](/win32/api/wingdi/ns-wingdi-displayconfig_rational) structure that contains the requested refresh rate for this path. **RefreshRate** must match a refresh rate supported by the driver for the specified resolution. This refresh rate is defined as progressive because remote drivers can only support progressive target modes.

### -field VSyncFreqDivider

The V Sync divider value for the specified **RefreshRate**.

### -field MonitorColorMode

A [**IDDCX_DISPLAYCONFIG_MONITOR_COLORMODE**](ne-iddcx-iddcx_displayconfig_monitor_colormode.md) value that specifies the color mode to be set on this monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
