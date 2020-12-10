---
UID: NE:d3dkmdt._DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
title: _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS (d3dkmdt.h)
description: The DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration identifies the semantics of a protected output that is created in a call to the DxgkDdiOPMCreateProtectedOutput function.
old-location: display\dxgkmdt_opm_video_output_semantics.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration"]
ms.keywords: DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration [Display Devices], DXGKMDT_OPM_VOS_COPP_SEMANTICS, DXGKMDT_OPM_VOS_OPM_SEMANTICS, DmEnums_246674bf-9e12-47c0-ab28-54c09d25fc43.xml, _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VOS_COPP_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VOS_OPM_SEMANTICS, display.dxgkmdt_opm_video_output_semantics
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.typenames: DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
f1_keywords:
 - _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
 - d3dkmdt/_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
 - DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
 - d3dkmdt/DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
---

# _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration


## -description

The DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration identifies the semantics of a protected output that is created in a call to the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a> function.

## -enum-fields

### -field DXGKMDT_OPM_VOS_COPP_SEMANTICS

Indicates that a protected output has Certified Output Protection Protocol (COPP) semantics.

### -field DXGKMDT_OPM_VOS_OPM_SEMANTICS

Indicates that a protected output has Output Protection Management (OPM) semantics.

### -field DXGKMDT_OPM_VOS_OPM_INDIRECT_DISPLAY

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_create_protected_output">DxgkDdiOPMCreateProtectedOutput</a>
