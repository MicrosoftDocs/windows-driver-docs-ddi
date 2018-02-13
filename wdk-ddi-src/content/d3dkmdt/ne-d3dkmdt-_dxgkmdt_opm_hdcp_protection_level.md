---
UID: NE:d3dkmdt._DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
title: "_DXGKMDT_OPM_HDCP_PROTECTION_LEVEL"
author: windows-driver-content
description: The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP).
old-location: display\dxgkmdt_opm_hdcp_protection_level.htm
old-project: display
ms.assetid: e0d38f3b-19da-4118-a1d9-7d5a00bcad26
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkmdt_opm_hdcp_protection_level, DXGKMDT_OPM_HDCP_FORCE_ULONG, _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_HDCP_PROTECTION_LEVEL, DmEnums_5df35ab3-a367-45c3-b03c-12b3d733f244.xml, DXGKMDT_OPM_HDCP_ON, d3dkmdt/DXGKMDT_OPM_HDCP_OFF, DXGKMDT_OPM_HDCP_OFF, d3dkmdt/DXGKMDT_OPM_HDCP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_HDCP_ON, DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration [Display Devices], DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_HDCP_PROTECTION_LEVEL
---

# _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration


## -description


The DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports High-bandwidth Digital Content Protection (HDCP). 


## -syntax


````
typedef enum _DXGKMDT_OPM_HDCP_PROTECTION_LEVEL { 
  DXGKMDT_OPM_HDCP_OFF          = 0,
  DXGKMDT_OPM_HDCP_ON           = 1,
  DXGKMDT_OPM_HDCP_FORCE_ULONG  = 0x7fffffff
} DXGKMDT_OPM_HDCP_PROTECTION_LEVEL;
````


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

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_HDCP_PROTECTION_LEVEL enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

