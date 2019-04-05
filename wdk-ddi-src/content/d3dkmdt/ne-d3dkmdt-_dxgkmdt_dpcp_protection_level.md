---
UID: NE:d3dkmdt._DXGKMDT_DPCP_PROTECTION_LEVEL
title: _DXGKMDT_DPCP_PROTECTION_LEVEL (d3dkmdt.h)
description: The DXGKMDT_OPM_DPCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports DisplayPort Content Protection (DPCP).
old-location: display\dxgkmdt_opm_dpcp_protection_level.htm
tech.root: display
ms.assetid: 7c21da9a-7629-41f8-addf-ac03927511c0
ms.date: 05/10/2018
ms.keywords: DXGKMDT_DPCP_PROTECTION_LEVEL, DXGKMDT_OPM_DPCP_FORCE_ULONG, DXGKMDT_OPM_DPCP_OFF, DXGKMDT_OPM_DPCP_ON, DXGKMDT_OPM_DPCP_PROTECTION_LEVEL, DXGKMDT_OPM_DPCP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_22bd45fa-ebe4-468e-8036-f3679619f51a.xml, _DXGKMDT_DPCP_PROTECTION_LEVEL, _DXGKMDT_DPCP_PROTECTION_LEVEL enumeration [Display Devices], d3dkmdt/DXGKMDT_OPM_DPCP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_DPCP_OFF, d3dkmdt/DXGKMDT_OPM_DPCP_ON, d3dkmdt/_DXGKMDT_DPCP_PROTECTION_LEVEL, display.dxgkmdt_opm_dpcp_protection_level
ms.topic: enum
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
- DXGKMDT_OPM_DPCP_PROTECTION_LEVEL
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_DPCP_PROTECTION_LEVEL
---

# _DXGKMDT_DPCP_PROTECTION_LEVEL enumeration


## -description


The DXGKMDT_OPM_DPCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports DisplayPort Content Protection (DPCP). 


## -enum-fields




### -field DXGKMDT_OPM_DPCP_OFF

Indicates that DPCP does not protect the output's signal. 


### -field DXGKMDT_OPM_DPCP_ON

Indicates that DPCP protects the output's signal. 


### -field DXGKMDT_OPM_DPCP_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -remarks



DPCP protects digital video signals from DisplayPort output connectors. For more information about DisplayPort, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=71382">DisplayPort article</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560921">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>
 

 

