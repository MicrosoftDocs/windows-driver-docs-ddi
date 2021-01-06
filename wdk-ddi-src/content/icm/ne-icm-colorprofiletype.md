---
UID: NE:icm.COLORPROFILETYPE
title: COLORPROFILETYPE (icm.h)
description: The COLORPROFILETYPE enumeration is used to specify the type of color profile.
old-location: print\colorprofiletype.htm
tech.root: print
ms.date: 08/13/2020
keywords: ["COLORPROFILETYPE enumeration"]
ms.keywords: "*PCOLORPROFILETYPE, COLORPROFILETYPE, COLORPROFILETYPE enumeration [Print Devices], CPT_CAMP, CPT_DMP, CPT_GMMP, CPT_ICC, colorfnc_409d0d83-91ea-408a-8970-4de6e9cf94eb.xml, icm/COLORPROFILETYPE, icm/CPT_CAMP, icm/CPT_DMP, icm/CPT_GMMP, icm/CPT_ICC, print.colorprofiletype"
req.header: icm.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- icm.h
api_name:
- COLORPROFILETYPE
targetos: Windows
req.typenames: COLORPROFILETYPE
---

# COLORPROFILETYPE enumeration

## -description

The COLORPROFILETYPE enumeration is used to specify the type of color profile.

## -enum-fields

### -field CPT_ICC

Specifies an ICC profile. If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of [COLORPROFILESUBTYPE](/previous-versions/ff546012(v=vs.85)) are valid.

### -field CPT_DMP

Specifies a WCS device model profile (DMP). If this value is specified, only the CPST_RGB_WORKING_SPACE and CPST_CUSTOM_WORKING_SPACE values of [COLORPROFILESUBTYPE](/previous-versions/ff546012(v=vs.85)) are valid.

### -field CPT_CAMP

Specifies a WCS color appearance model profile (CAMP). If this value is specified, only the CPST_NONE value of [COLORPROFILESUBTYPE](/previous-versions/ff546012(v=vs.85)) is valid.

### -field CPT_GMMP

Specifies a WCS gamut map model profile (GMMP). If this value is specified, only the CPST_PERCEPTUAL, CPST_SATURATION, CPST_RELATIVE_COLORIMETRIC, and CPST_ABSOLUTE_COLORIMETRIC values of [COLORPROFILESUBTYPE](/previous-versions/ff546012(v=vs.85)) are valid. Any one of these values may optionally be combined (in a bitwise OR operation) with CPST_DEFAULT.

## -remarks

The PCOLORPROFILETYPE and LPCOLORPROFILETYPE data types are defined as pointers to this enumeration:

```cpp
typedef COLORPROFILETYPE *PCOLORPROFILETYPE, *LPCOLORPROFILETYPE;
```

## -see-also

[COLORPROFILESUBTYPE](/previous-versions/ff546012(v=vs.85))
