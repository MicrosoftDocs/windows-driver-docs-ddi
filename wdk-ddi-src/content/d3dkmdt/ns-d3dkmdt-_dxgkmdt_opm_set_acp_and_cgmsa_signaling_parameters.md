---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
title: _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS (d3dkmdt.h)
description: The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.
old-location: display\dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure"]
ms.keywords: DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure [Display Devices], DmStructs_64a3857d-3c66-4653-980b-72df307eba0f.xml, _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, d3dkmdt/DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, display.dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters
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
req.typenames: DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
f1_keywords:
 - _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
 - d3dkmdt/_DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
 - DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
 - d3dkmdt/DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
---

# _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure


## -description

The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.

## -struct-fields

### -field ulNewTVProtectionStandard

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_protection_standard">DXGKMDT_OPM_PROTECTION_STANDARD</a>-typed value that indicates the type of television signal to set ACP and CGMS-A signaling for on the protected output.

### -field ulAspectRatioChangeMask1

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData1</b> member.

### -field ulAspectRatioData1

32-bit data that indicates the aspect ratio value to set for the active protection standard.

### -field ulAspectRatioChangeMask2

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData2</b> member.

### -field ulAspectRatioData2

32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.

### -field ulAspectRatioChangeMask3

A mask value that indicates the valid bits to change in the following <b>ulAspectRatioData3</b> member.

### -field ulAspectRatioData3

32-bit data for additional aspect ratio-related data for specific protection standards. This data can be used to express End and Q0 values for EIA-608-B, or active format description for CEA-805-A Type B packets.

### -field ulReserved

Reserved. Must be set to zero.

### -field ulReserved2

Reserved. Must be set to zero.

### -field ulReserved3

Reserved. Must be set to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_protection_standard">DXGKMDT_OPM_PROTECTION_STANDARD</a>
