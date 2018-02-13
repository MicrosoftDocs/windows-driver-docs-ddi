---
UID: NE:d3dkmdt._DXGKMDT_OPM_CGMSA
title: "_DXGKMDT_OPM_CGMSA"
author: windows-driver-content
description: The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A).
old-location: display\dxgkmdt_opm_cgmsa.htm
old-project: display
ms.assetid: 1318d00e-aac3-4ff2-89a2-bcabcdff6331
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmEnums_94737355-e3ff-4e00-9dbe-9d954e462f54.xml, d3dkmdt/DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NEVER, DXGKMDT_OPM_CGMSA_COPY_NO_MORE, d3dkmdt/DXGKMDT_OPM_CGMSA, _DXGKMDT_OPM_CGMSA, d3dkmdt/DXGKMDT_OPM_CGMSA_OFF, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_FREELY, DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION, DXGKMDT_OPM_CGMSA_COPY_NEVER, DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED, DXGKMDT_OPM_CGMSA_OFF, d3dkmdt/DXGKMDT_OPM_CGMSA_COPY_NO_MORE, DXGKMDT_OPM_CGMSA_COPY_FREELY, DXGKMDT_OPM_CGMSA enumeration [Display Devices], DXGKMDT_OPM_CGMSA, display.dxgkmdt_opm_cgmsa
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
-	DXGKMDT_OPM_CGMSA
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_CGMSA
---

# _DXGKMDT_OPM_CGMSA enumeration


## -description


The DXGKMDT_OPM_CGMSA enumeration indicates the protection levels for a protected output that supports Content Generation Management System Analog (CGMS-A). 


## -syntax


````
typedef enum _DXGKMDT_OPM_CGMSA { 
  DXGKMDT_OPM_CGMSA_OFF                        = 0,
  DXGKMDT_OPM_CGMSA_COPY_FREELY                = 1,
  DXGKMDT_OPM_CGMSA_COPY_NO_MORE               = 2,
  DXGKMDT_OPM_CGMSA_COPY_ONE_GENERATION        = 3,
  DXGKMDT_OPM_CGMSA_COPY_NEVER                 = 4,
  DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED  = 0x08
} DXGKMDT_OPM_CGMSA;
````


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

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED corresponds to the CEA-805-A standard's Redistribution Control Information (RCI) bit. For more information about the RCI bit, see the definition of the RCI bit in section 4.4.3.8 in the CEA-805-A standard. For more information about this standard, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=71276">Consumer Electronics Association</a> website. 

DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED can be used only if a protected output has COPP semantics. A protected output must enable redistribution control if the DirectX graphics kernel subsystem passes DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a> function. <i>DxgkDdiOPMConfigureProtectedOutput</i> must fail if DXGKMDT_OPM_REDISTRIBUTION_CONTROL_REQUIRED is passed to it and the display miniport driver cannot enable redistribution control for any reason. 


## -remarks



CGMS-A protects analog TV signals. Currently, OPM can use CGMS-A to protect signals from composite outputs, S-Video outputs, or component outputs. For more information about CGMS-A, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70568">CGMS-A article</a>. 




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_configure_protected_output.md">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md">DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_CGMSA enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

