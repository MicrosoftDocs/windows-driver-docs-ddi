---
UID: NS:d3dkmddi._DXGK_COLORIMETRY
title: _DXGK_COLORIMETRY (d3dkmddi.h)
description: Describes colorimetry and closely related fields used to describe overrides from the descriptor retrieved from the display device.
old-location: display\dxgk_colorimetry.htm
ms.date: 05/10/2018
keywords: ["DXGK_COLORIMETRY structure"]
ms.keywords: "*PDXGK_COLORIMETRY, DXGK_COLORIMETRY, DXGK_COLORIMETRY structure [Display Devices], PDXGK_COLORIMETRY, PDXGK_COLORIMETRY structure pointer [Display Devices], _DXGK_COLORIMETRY, d3dkmddi/DXGK_COLORIMETRY, d3dkmddi/PDXGK_COLORIMETRY, display.dxgk_colorimetry"
req.header: d3dkmddi.h
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
tech.root: display
req.typenames: DXGK_COLORIMETRY, *PDXGK_COLORIMETRY
f1_keywords:
 - _DXGK_COLORIMETRY
 - d3dkmddi/_DXGK_COLORIMETRY
 - PDXGK_COLORIMETRY
 - d3dkmddi/PDXGK_COLORIMETRY
 - DXGK_COLORIMETRY
 - d3dkmddi/DXGK_COLORIMETRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_COLORIMETRY
---

# _DXGK_COLORIMETRY structure


## -description

Describes colorimetry and closely related fields used to describe overrides from the descriptor retrieved from the display device.

## -struct-fields

### -field RedPoint

Override for display red point.  Note, each dimension is a 10-bit value stored in the least significant bits.
Zero indicates no override.

### -field GreenPoint

Override for display green point. Note, each dimension is a 10-bit value stored in the least significant bits.

### -field BluePoint

Override for display blue point. Note, each dimension is a 10-bit value stored in the least significant bits.

### -field WhitePoint

Override for display white point. Note, each dimension is a 10-bit value stored in the least significant bits.

### -field MinLuminance

Override for the minimum luminance value supported by the display measured in one ten thousandth of a nit.  Only valid if MaxLuminance is non-zero.  Zero is a valid value.

### -field MaxLuminance

Override for the maximum luminance value supported by the display measured in one ten thousandth of a nit.  This luminance level is expected to be supported for only a relatively small area in any given frame.  
Zero indicates no override of MaxLuminance, MaxFullFrameLuminance or MinLuminance.

### -field MaxFullFrameLuminance

Override for the max full frame luminance value supported by the display measured in one ten thousandth of a nit.  This luminance level must be supported across every pixel in the frame simultaneously in order to provide an estimate of the average luminance value which can be supported by the display across a frame.
Only valid if MaxLuminance is non-zero.  Zero is not a valid override.

### -field FormatBitDepths

Overrides the supported bits per color channel in each of the five color encodings specified for wire-formats.  At least one bit must be set, excluding the Preference field which is reserved and must be zero.

### -field StandardColorimetryFlags

Indicates support for specific colorimetry and EOTF capabilities using bit-fields.

## -remarks

This struct is used both for querying overrides from the driver, and for the OS reporting the final set of values it has selected.  Overrides are supported for integrated displays using this structure which is embedded within the DXGK_QUERYINTEGRATEDDISPLAYOUT struct and for external displays where this stuct is used as the output buffer is for an adapter query type DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES.  The selected and adjusted overrides are reported back to the driver using DxgkDdiSetTargetAdjustedColorimetry.



When querying overrides, the OS requires that either all fields are filled by the driver or the buffer is left zeroed to avoid the complexity of attempting to merge these inter-related attributes from different sources. If the struct is not completely zeroed, the OS validates that fields which must not be zero as noted above, are not zero.  



The color points are further validated beyond a simple sanity check (each value must be between 1 and 1023) to ensure reasonable values by comparing the coordinates of each point to the standard points and ensuring that none is too far away from the standard.



When the OS calls DxgkDdiSetTargetAdjustedColorimetry, the FormatBitDepths and StandardColorimetryFlags are zeroed as these are capability fields so only valid in queries.

