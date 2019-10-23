---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
title: _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS (d3dkmdt.h)
description: The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the DxgkDdiOPMConfigureProtectedOutput function.
old-location: display\dxgkmdt_opm_set_protection_level_parameters.htm
tech.root: display
ms.assetid: e5b35b0d-c7ad-4a67-8552-13df4c9c2b84
ms.date: 05/10/2018
ms.keywords: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure [Display Devices], DmStructs_9d43af01-039a-4f68-8583-b42ae54a5bbe.xml, _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, d3dkmdt/DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS, display.dxgkmdt_opm_set_protection_level_parameters
ms.topic: struct
f1_keywords:
 - "d3dkmdt/DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS"
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
- DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS
---

# _DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure


## -description


The DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS structure contains parameters to set the protection level of a protected output in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a> function.


## -struct-fields




### -field ulProtectionType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_protection_type">DXGKMDT_OPM_PROTECTION_TYPE</a>-typed value that indicates the protection type to set a protection level for. 


### -field ulProtectionLevel

A value that specifies the protection level to set for one of the following protection types that is specified in the <b>ulProtectionType</b> member:  





#### DXGKMDT_OPM_PROTECTION_TYPE_ACP

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_acp_protection_level">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>-typed value that identifies the Analog Copy Protection (ACP) level that the protected output uses.



#### DXGKMDT_OPM_PROTECTION_TYPE_CGMSA

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_cgmsa">DXGKMDT_OPM_CGMSA</a>-typed value that identifies the Content Generation Management System Analog (CGMS-A) protection level that the protected output uses.



#### DXGKMDT_OPM_PROTECTION_TYPE_HDCP or DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_hdcp_protection_level">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>-typed value that identifies the High-bandwidth Digital Content Protection (HDCP) level that the protected output uses. Protected outputs with COPP semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP; protected outputs with OPM semantics can use only DXGKMDT_OPM_PROTECTION_TYPE_HDCP. 



#### DXGKMDT_OPM_PROTECTION_TYPE_DPCP

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_dpcp_protection_level">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>-typed value that identifies the DisplayPort Copy Protection (DPCP) protection level that the protected output uses.


### -field Reserved

Reserved. Must be set to zero. 


### -field Reserved2

Reserved. Must be set to zero. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_acp_protection_level">DXGKMDT_OPM_ACP_PROTECTION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_cgmsa">DXGKMDT_OPM_CGMSA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_dpcp_protection_level">DXGKMDT_OPM_DPCP_PROTECTION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_hdcp_protection_level">DXGKMDT_OPM_HDCP_PROTECTION_LEVEL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_protection_type">DXGKMDT_OPM_PROTECTION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output">DxgkDdiOPMConfigureProtectedOutput</a>
 

 

