---
UID: NE:d3dkmdt._DXGKMDT_OPM_CGMSA
title: _DXGKMDT_OPM_CGMSA (d3dkmdt.h)
description: The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A).
old-location: display\dxgkmdt_opm_cgmsa.htm
tech.root: display
ms.assetid: 1318d00e-aac3-4ff2-89a2-bcabcdff6331
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_CGMSA enumeration"]
ms.keywords: DXGKMDT_OPM_CGMSA, DXGKMDT_OPM_CGMSA enumeration [Display Devices], DXGKMDT_OPM_CGMSA_COPY_FREELY, DXGKMDT_OPM_CGMSA_COPY_NEVER, DXGKMDT_OPM_CGMSA_COPY_NO_MORE, DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, DXGKMDT_OPM_CGMSA_OFF, DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, DmEnums_94737355-e3ff-4e00-9dbe-9d954e462f54.xml, _DXGKMDT_OPM_CGMSA, d3dkmdt/DXGKMDT_OPM_CGMSA, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_FREELY, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NEVER, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NO_MORE, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, d3dkmdt/DXGKMDT_OPM_CGMSA_OFF, d3dkmdt/DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, display.dxgkmdt_opm_cgmsa
f1_keywords:
 - "d3dkmdt/DXGKMDT_OPM_CGMSA"
 - "DXGKMDT_OPM_CGMSA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- DXGKMDT_OPM_CGMSA
targetos: Windows
req.typenames: DXGKMDT_OPM_CGMSA
---

# _DXGKMDT_OPM_CGMSA enumeration


## -description


The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A). 


## -enum-fields




### -field DXGKMDT_OPM_CGMSA_OFF

Indicates that a video output's signal is not protected with the CGMS-A output protection scheme. 


### -field DXGKMDT_OPM_CGMSA_COPY_FREELY

Indicates that the signal from a physical video output can be copied an infinite number of times. 


### -field DXGKMDT_OPM_CGMSA_COPY_NO_MORE

Indicates that the signal from a physical video output cannot be copied because the signal was already copied once. 


### -field DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION

Indicates that the signal from a physical video output can be copied once. However, the copy can never be copied. 


### -field DXGKMDT_OPM_CGMSA_COPY_NEVER

Indicates that the signal from a physical video output can never be copied. 


### -field DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED

Indicates that the technological control of consumer redistribution is enabled. 

The five preceding protection levels can be bitwise OR combined  with the DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED to turn on redistribution control. 

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED corresponds to the CEA-805-A standard's Redistribution Control Information (RCI) bit. For more information about the RCI bit, see the definition of the RCI bit in section 4.4.3.8 in the CEA-805-A standard. For more information about this standard, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=71276">Consumer Electronics Association</a> website. 

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED can be used only if a protected output has COPP semantics. A protected output must enable redistribution control if the DirectX graphics kernel subsystem passes DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a> function. <i>DxgkDdiOPMConfigureProtectedOutput</i> must fail if DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED is passed to it and the display miniport driver cannot enable redistribution control for any reason. 


## -remarks



CGMS-A protects analog TV signals. Currently, OPM can use CGMS-A to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about CGMS-A, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=70568">CGMS-A article</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_standard_information">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>
 

 

