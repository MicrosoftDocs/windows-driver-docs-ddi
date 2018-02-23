---
UID: NS:d3dkmdt._DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
title: "_DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS"
author: windows-driver-content
description: The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.
old-location: display\dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters.htm
old-project: display
ms.assetid: e4151e72-e0a6-4873-a2e8-c3321941cfd4
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgkmdt_opm_set_acp_and_cgmsa_signaling_parameters, DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure [Display Devices], d3dkmdt/DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS, DmStructs_64a3857d-3c66-4653-980b-72df307eba0f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS
---

# _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure


## -description


The DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure contains parameters to set Analog Content Protection (ACP) and Content Generation Management System Analog (CGMS-A) signaling for a protected output.


## -syntax


````
typedef struct _DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS {
  ULONG ulNewTVProtectionStandard;
  ULONG ulAspectRatioChangeMask1;
  ULONG ulAspectRatioData1;
  ULONG ulAspectRatioChangeMask2;
  ULONG ulAspectRatioData2;
  ULONG ulAspectRatioChangeMask3;
  ULONG ulAspectRatioData3;
  ULONG ulReserved[4];
  ULONG ulReserved2[4];
  ULONG ulReserved3;
} DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS;
````


## -struct-fields




### -field ulNewTVProtectionStandard

A <a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_standard.md">DXGKMDT_OPM_PROTECTION_STANDARD</a>-typed value that indicates the type of television signal to set ACP and CGMS-A signaling for on the protected output. 


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

<a href="..\d3dkmdt\ne-d3dkmdt-_dxgkmdt_opm_protection_standard.md">DXGKMDT_OPM_PROTECTION_STANDARD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_SET_ACP_AND_CGMSA_SIGNALING_PARAMETERS structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

