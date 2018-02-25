---
UID: NE:d3dkmdt._DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
title: "_DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS"
author: windows-driver-content
description: The DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration identifies the semantics of a protected output that is created in a call to the DxgkDdiOPMCreateProtectedOutput function.
old-location: display\dxgkmdt_opm_video_output_semantics.htm
old-project: display
ms.assetid: f399e597-df5e-4dab-8c35-d43803e33bcd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration [Display Devices], DXGKMDT_OPM_VOS_COPP_SEMANTICS, DXGKMDT_OPM_VOS_OPM_SEMANTICS, DmEnums_246674bf-9e12-47c0-ab28-54c09d25fc43.xml, E, G, I, K, M, N, O, P, S, T, U, V, X, _, _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VOS_COPP_SEMANTICS, d3dkmdt/DXGKMDT_OPM_VOS_OPM_SEMANTICS, display.dxgkmdt_opm_video_output_semantics"
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
-	DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS
---

# _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration


## -description


The DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration identifies the semantics of a protected output that is created in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function. 


## -syntax


````
typedef enum _DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS { 
  DXGKMDT_OPM_VOS_COPP_SEMANTICS  = 0,
  DXGKMDT_OPM_VOS_OPM_SEMANTICS   = 1
} DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS;
````


## -enum-fields




### -field DXGKMDT_OPM_VOS_COPP_SEMANTICS

Indicates that a protected output has Certified Output Protection Protocol (COPP) semantics. 


### -field DXGKMDT_OPM_VOS_OPM_SEMANTICS

Indicates that a protected output has Output Protection Management (OPM) semantics. 


### -field DXGKMDT_OPM_VOS_OPM_INDIRECT_DISPLAY




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_VIDEO_OUTPUT_SEMANTICS enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

