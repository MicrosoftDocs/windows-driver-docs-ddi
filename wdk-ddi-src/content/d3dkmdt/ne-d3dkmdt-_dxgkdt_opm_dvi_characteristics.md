---
UID: NE:d3dkmdt._DXGKDT_OPM_DVI_CHARACTERISTICS
title: _DXGKDT_OPM_DVI_CHARACTERISTICS (d3dkmdt.h)
description: The DXGKDT_OPM_DVI_CHARACTERISTICS enumeration indicates the Digital Video Interface (DVI) electrical characteristics of a connector.
old-location: display\dxgkdt_opm_dvi_characteristics.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKDT_OPM_DVI_CHARACTERISTICS enumeration"]
ms.keywords: DXGKDT_OPM_DVI_CHARACTERISTICS, DXGKDT_OPM_DVI_CHARACTERISTICS enumeration [Display Devices], DXGKMDT_OPM_DVI_CHARACTERISTICS_FORCE_ULONG, DXGKMDT_OPM_DVI_CHARACTERISTIC_1_0, DXGKMDT_OPM_DVI_CHARACTERISTIC_1_1_OR_ABOVE, DmEnums_4bcf670e-2b55-4278-80a4-71c7c820dae6.xml, _DXGKDT_OPM_DVI_CHARACTERISTICS, d3dkmdt/DXGKDT_OPM_DVI_CHARACTERISTICS, d3dkmdt/DXGKMDT_OPM_DVI_CHARACTERISTICS_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_DVI_CHARACTERISTIC_1_0, d3dkmdt/DXGKMDT_OPM_DVI_CHARACTERISTIC_1_1_OR_ABOVE, display.dxgkdt_opm_dvi_characteristics
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.typenames: DXGKDT_OPM_DVI_CHARACTERISTICS
f1_keywords:
 - _DXGKDT_OPM_DVI_CHARACTERISTICS
 - d3dkmdt/_DXGKDT_OPM_DVI_CHARACTERISTICS
 - DXGKDT_OPM_DVI_CHARACTERISTICS
 - d3dkmdt/DXGKDT_OPM_DVI_CHARACTERISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKDT_OPM_DVI_CHARACTERISTICS
 - DXGKDT_OPM_DVI_CHARACTERISTICS
---

# _DXGKDT_OPM_DVI_CHARACTERISTICS enumeration


## -description

The DXGKDT_OPM_DVI_CHARACTERISTICS enumeration indicates the Digital Video Interface (DVI) electrical characteristics of a connector.

## -enum-fields

### -field DXGKMDT_OPM_DVI_CHARACTERISTIC_1_0

Indicates that the DVI electrical characteristics are version 1.0.

### -field DXGKMDT_OPM_DVI_CHARACTERISTIC_1_1_OR_ABOVE

Indicates that the DVI electrical characteristics are version 1.1 or later.

### -field DXGKMDT_OPM_DVI_CHARACTERISTICS_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks

The DXGKMDT_OPM_GET_DVI_CHARACTERISTICS GUID is used in a call to the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> function to retrieve the DVI electrical characteristics of the output connector. For more information about retrieving information about a protected output, see <a href="/windows-hardware/drivers/display/retrieving-information-about-a-protected-output">Retrieving Information About a Protected Output</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>

