---
UID: NE:d3dkmdt._DXGKMDT_OPM_ACP_PROTECTION_LEVEL
title: "_DXGKMDT_OPM_ACP_PROTECTION_LEVEL"
author: windows-driver-content
description: The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP).
old-location: display\dxgkmdt_opm_acp_protection_level.htm
tech.root: display
ms.assetid: 9a7bceab-2bf7-4148-b62a-7d03f61aa9fa
ms.date: 05/10/2018
ms.keywords: DXGKMDT_OPM_ACP_FORCE_ULONG, DXGKMDT_OPM_ACP_LEVEL_ONE, DXGKMDT_OPM_ACP_LEVEL_THREE, DXGKMDT_OPM_ACP_LEVEL_TWO, DXGKMDT_OPM_ACP_OFF, DXGKMDT_OPM_ACP_PROTECTION_LEVEL, DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_8ddb5546-7305-4b58-85e9-8e38a9bdf8af.xml, _DXGKMDT_OPM_ACP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_ACP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_ONE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_THREE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_TWO, d3dkmdt/DXGKMDT_OPM_ACP_OFF, d3dkmdt/DXGKMDT_OPM_ACP_PROTECTION_LEVEL, display.dxgkmdt_opm_acp_protection_level
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_ACP_PROTECTION_LEVEL
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_ACP_PROTECTION_LEVEL
---

# _DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration


## -description


The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP). 


## -enum-fields




### -field DXGKMDT_OPM_ACP_OFF

Indicates that the signal from a video output is not protected by any form of ACP.


### -field DXGKMDT_OPM_ACP_LEVEL_ONE

Indicates that the signal from a video output is protected by the ACP level one protection scheme. 


### -field DXGKMDT_OPM_ACP_LEVEL_TWO

Indicates that the signal from a video output is protected by the ACP level two protection scheme. 


### -field DXGKMDT_OPM_ACP_LEVEL_THREE

Indicates that the signal from a video output is protected by the ACP level three protection scheme. 


### -field DXGKMDT_OPM_ACP_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.


## -remarks



ACP protects analog TV signals. For example, a DVD player can use ACP to prevent a VCR from recording a copy of a DVD movie. Currently, OPM can use ACP to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about ACP, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=71273">Rovi (formerly Macrovision)</a> website.

Display miniport drivers use the values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL to report the virtual protection level of the protected output or the actual protection level of a physical connector through calls to the driver's <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> and <a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions. The values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL are also used to configure the protected output's new virtual protection level in a call to the driver's <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560921">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>
 

 

