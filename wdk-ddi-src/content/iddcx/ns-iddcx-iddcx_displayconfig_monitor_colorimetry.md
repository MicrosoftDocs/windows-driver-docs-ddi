---
UID: NS:iddcx.IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
tech.root: display
title: IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY structure.
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
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
f1_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
 - iddcx/IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY
---

## -description

The **IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY** structure contains colorimetry information for a monitor.

## -struct-fields

### -field RedPoint

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains an override for the display red point. Each dimension is a 10-bit value stored in the least significant bits. Zero indicates no override.

### -field GreenPoint

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains an override for the display green point. Each dimension is a 10-bit value stored in the least significant bits.

### -field BluePoint

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains an override for the display blue point. Each dimension is a 10-bit value stored in the least significant bits.

### -field WhitePoint

A [**DISPLAYCONFIG_2DREGION**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_2dregion) structure that contains an override for the display white point. Each dimension is a 10-bit value stored in the least significant bits.

### -field MinLuminance

Override for the minimum luminance value supported by the display, measured in one ten thousandth of a nit. Zero is a valid value. **MinLuminance** is valid only if MaxLuminance is non-zero.

### -field MaxLuminance

Override for the maximum luminance value supported by the display, measured in one ten thousandth of a nit. This luminance level is expected to be supported for only a relatively small area in any given frame. Zero indicates no override of **MaxLuminance**, **MaxFullFrameLuminance** or **MinLuminance**.

### -field MaxFullFrameLuminance

Override for the maximum full frame luminance value supported by the display, measured in one ten thousandth of a nit. This luminance level must be supported across every pixel in the frame simultaneously in order to provide an estimate of the average luminance value that the display can support across a frame. **MaxFullFrameLuminance** is only valid if **MaxLuminance** is non-zero. Zero is not a valid override.

### -field BitsPerComponent

A [**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md) structure that overrides the supported bits per color component in each of the color encodings specified. At least one bit must be set one of the color encodings.

### -field Flags

A bitwise OR of[**IDDCX_DISPLAYCONFIG_MONITOR_COLORIMETRY_FLAGS**](ne-iddcx-iddcx_displayconfig_monitor_colorimetry_flags.md) enumeration flags that indicates support for specific colorimetry and Electro-Optical Transfer Function (EOTF) capabilities.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2**](ns-iddcx-idarg_in_adapterdisplayconfigupdate2.md)

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
