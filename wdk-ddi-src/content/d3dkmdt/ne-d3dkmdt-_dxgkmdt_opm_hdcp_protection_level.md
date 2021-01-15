---
UID: NE:d3dkmdt._DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
title: _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL (d3dkmdt.h)
description: The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP).
old-location: display\dxgkmdt_opm_hdcp_protection_level.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration"]
ms.keywords: DXGKMDT_OPM_HDCP_FORCE_ULONG, DXGKMDT_OPM_HDCP_OFF, DXGKMDT_OPM_HDCP_ON, DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_5df35ab3-a367-45c3-b03c-12b3d733f244.xml, _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_HDCP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_HDCP_OFF, d3dkmdt/DXGKMDT_OPM_HDCP_ON, d3dkmdt/DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, display.dxgkmdt_opm_hdcp_protection_level
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
req.typenames: DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
f1_keywords:
 - _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
 - d3dkmdt/_DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
 - DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
 - d3dkmdt/DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
 - DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
---

# _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration


## -description

The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP).

## -enum-fields

### -field DXGKMDT_OPM_HDCP_OFF

Indicates that HDCP does not protect the output's signal.

### -field DXGKMDT_OPM_HDCP_ON

Indicates that HDCP protects the output's signal.

### -field DXGKMDT_OPM_HDCP_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks

HDCP protects digital video signals from digital video output connectors. Currently, OPM can use HDCP to protect data from Digital Video Interface (DVI) and High-Definition Multimedia Interface (HDMI) connector outputs. For more information about the HDCP system, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>

