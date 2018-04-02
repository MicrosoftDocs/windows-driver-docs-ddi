---
UID: NE:d3dkmdt._DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
title: "_DXGKMDT_OPM_HDCP_PROTECTION_LEVEL"
author: windows-driver-content
description: The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP).
old-location: display\dxgkmdt_opm_hdcp_protection_level.htm
old-project: display
ms.assetid: e0d38f3b-19da-4118-a1d9-7d5a00bcad26
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKMDT_OPM_HDCP_FORCE_ULONG, DXGKMDT_OPM_HDCP_OFF, DXGKMDT_OPM_HDCP_ON, DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_5df35ab3-a367-45c3-b03c-12b3d733f244.xml, _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_HDCP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_HDCP_OFF, d3dkmdt/DXGKMDT_OPM_HDCP_ON, d3dkmdt/DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, display.dxgkmdt_opm_hdcp_protection_level
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
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



HDCP protects digital video signals from digital video output connectors. Currently, OPM can use HDCP to protect data from Digital Video Interface (DVI) and High-Definition Multimedia Interface (HDMI) connector outputs. For more information about the HDCP system, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560921">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560925">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/9f15df1e-bdf5-4634-97f1-78515664b594">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a>
 

 

