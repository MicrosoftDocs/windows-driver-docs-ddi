---
UID: NS:iddcx.IDDCX_DISPLAYCONFIGPATH2
tech.root: display
title: IDDCX_DISPLAYCONFIGPATH2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIGPATH2 structure.
prerelease: false
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
 - IDDCX_DISPLAYCONFIGPATH2
f1_keywords:
 - IDDCX_DISPLAYCONFIGPATH2
 - iddcx/IDDCX_DISPLAYCONFIGPATH2
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIGPATH2
---

## -description

A **IDDCX_DISPLAYCONFIGPATH2** structure contains path display configuration information.

## -struct-fields

### -field Size

Size, in bytes, of this structure.

### -field Flags

A bitwise OR of [**IDDCX_DISPLAYCONFIGPATH2_FLAGS**](ne-iddcx-iddcx_displayconfigpath2_flags.md) values that identify the flags for this path, including which fields contain valid data.

### -field MonitorObject

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object handle that the driver provides to identify the monitor this path is targeted at.

### -field Mode

If valid, this field is a [**IDDCX_DISPLAYCONFIG_MODE**](ns-iddcx-iddcx_displayconfig_mode.md) structure that contains details of the mode to be set for the monitor in this path.

### -field MonitorScaleFactor

If valid, this field specifies the requested monitor DPI for this path. This value is just a hint and OS may override it to ensure the DPI configuration of the session is valid. Valid values are 100 to 500 inclusive.

### -field MonitorPhysicalSize

If valid, this field is a [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains the physical width and height override for the specified monitor, in millimeters. A value of zero means no override.

### -field MonitorColorimetry

If valid, this field is a [**IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY**](ns-iddcx-iddcx_displayconfig_monitor_colorimetry.md) structure that contains the colorimetry details for the specified monitor.

### -field MonitorSdrWhiteLevel

If valid, this field specifies the new white level, in nits, to be used for SDR content on this monitor when in an HDR mode.

## -remarks

An indirect display driver (IDD) calls [**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md) when it receives a new display configuration. It passes an array of **IDDCX_DISPLAYCONFIGPATH2** structures in [**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md).

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
