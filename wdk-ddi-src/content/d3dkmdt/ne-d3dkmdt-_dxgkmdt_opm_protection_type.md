---
UID: NE:d3dkmdt._DXGKMDT_OPM_PROTECTION_TYPE
title: _DXGKMDT_OPM_PROTECTION_TYPE (d3dkmdt.h)
description: The DXGKMDT_OPM_PROTECTION_TYPE enumeration indicates the type of protections that a video output supports.
old-location: display\dxgkmdt_opm_protection_type.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_PROTECTION_TYPE enumeration"]
ms.keywords: DXGKMDT_OPM_PROTECTION_TYPE, DXGKMDT_OPM_PROTECTION_TYPE enumeration [Display Devices], DXGKMDT_OPM_PROTECTION_TYPE_ACP, DXGKMDT_OPM_PROTECTION_TYPE_CGMSA, DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, DXGKMDT_OPM_PROTECTION_TYPE_DPCP, DXGKMDT_OPM_PROTECTION_TYPE_HDCP, DXGKMDT_OPM_PROTECTION_TYPE_MASK, DXGKMDT_OPM_PROTECTION_TYPE_NONE, DXGKMDT_OPM_PROTECTION_TYPE_OTHER, DmEnums_8213d95c-c1df-4084-b386-cfb9fac440e0.xml, _DXGKMDT_OPM_PROTECTION_TYPE, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_ACP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_CGMSA, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_DPCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_HDCP, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_MASK, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_NONE, d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE_OTHER, display.dxgkmdt_opm_protection_type
req.header: d3dkmdt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGKMDT_OPM_PROTECTION_TYPE
f1_keywords:
 - _DXGKMDT_OPM_PROTECTION_TYPE
 - d3dkmdt/_DXGKMDT_OPM_PROTECTION_TYPE
 - DXGKMDT_OPM_PROTECTION_TYPE
 - d3dkmdt/DXGKMDT_OPM_PROTECTION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_PROTECTION_TYPE
---

# _DXGKMDT_OPM_PROTECTION_TYPE enumeration

## -description

The DXGKMDT_OPM_PROTECTION_TYPE enumeration indicates the type of protections that a video output supports.

## -enum-fields

### -field DXGKMDT_OPM_PROTECTION_TYPE_OTHER

Indicates a protection type other than those given in the following constants of this enumeration.

### -field DXGKMDT_OPM_PROTECTION_TYPE_NONE

Indicates that the video output does not support any protection type.

### -field DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP

Indicates that the protected output supports High-bandwidth Digital Content Protection (HDCP) that is compatible with Certified Output Protection Protocol (COPP). For more information about HDCP, see the [HDCP Specification Revision 1.1](https://www.digital-cp.com/). This protection type can be used only with protected output objects that have COPP semantics. OPM can use this value in a call to the display miniport driver's [**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) function to determine whether a protected output supports COPP-compatible HDCP. OPM can also use this value in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to change the COPP-compatible HDCP protection level.

### -field DXGKMDT_OPM_PROTECTION_TYPE_ACP

Indicates that the protected output supports [Analog Copy Protection (ACP)](https://business.tivo.com/services/acp-technology). ACP protects analog TV signals. Currently, OPM can use ACP to protect signals from composite outputs, S-Video outputs, or component outputs. OPM can use this value in a call to the display miniport driver's [**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) function to determine whether a protected output supports ACP. OPM can also use this value in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to change the ACP protection level.

### -field DXGKMDT_OPM_PROTECTION_TYPE_CGMSA

Indicates that the protected output supports Content Generation Management System Analog (CGMS-A). CGMS-A protects analog TV signals. Currently, OPM can use CGMS-A to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about CGMS-A, see the [CGMS-A article](https://wikipedia.org/wiki/CGMS-A). OPM can use this value in a call to the display miniport driver's [**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) function to determine whether a protected output supports CGMS-A. OPM can also use this value in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to change the CGMS-A protection level.

### -field DXGKMDT_OPM_PROTECTION_TYPE_HDCP

Indicates that the protected output supports HDCP. This protection type can be used only with protected output objects that have OPM semantics. OPM can use this value in a call to the display miniport driver's [**DxgkDdiOPMGetInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md) function to determine whether a protected output supports HDCP. OPM can also use this value in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to change the HDCP protection level.

### -field DXGKMDT_OPM_PROTECTION_TYPE_DPCP

Indicates that the protected output supports DisplayPort Copy Protection (DPCP). For more information about DisplayPort, see the [DisplayPort article](https://wikipedia.org/wiki/DisplayPort). This protection type can be used only with protected output objects that have OPM semantics. OPM can use this value in a call to the display miniport driver's [**DxgkDdiOPMGetInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md) function to determine whether a protected output supports DPCP. OPM can also use this value in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function to change the DPCP protection level.

### -field DXGKMDT_OPM_PROTECTION_TYPE_TYPE_ENFORCEMENT_HDCP

### -field DXGKMDT_OPM_PROTECTION_TYPE_MASK

A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration.

## -remarks

DXGKMDT_OPM_PROTECTION_TYPE_HDCP and DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP are used to turn HDCP on or off and to determine if HDCP is on or off.

If a protected output supports DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP, it supports HDCP repeaters, and an application handles HDCP revocation. If a protected output supports DXGKMDT_OPM_PROTECTION_TYPE_HDCP, it supports HDCP repeaters and handles HDCP revocation.

## -see-also

[**DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md)

[**DXGKMDT_OPM_STANDARD_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_standard_information.md)

[**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

[**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[**DxgkDdiOPMGetInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md)
