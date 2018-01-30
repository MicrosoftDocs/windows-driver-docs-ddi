---
UID: NE:d3d10umddi.D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
title: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
author: windows-driver-content
description: The D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration type contains values that identify quality levels for multisample patterns.
old-location: display\d3d10_1_ddiarg_standard_multisample_quality_levels.htm
old-project: display
ms.assetid: 47c285fa-f53a-4e35-ad66-bf14dfc9f80e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration [Display Devices], display.d3d10_1_ddiarg_standard_multisample_quality_levels, d3d10umddi/D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS, D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN, d3d10umddi/D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS, d3d10umddi/D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN, UMDisplayDriver_Dx10param_Structs_b617a227-3358-4b23-918f-9603c8fed13e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	d3d10umddi.h
apiname:
-	D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
product: Windows
targetos: Windows
req.typenames: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
---

# D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration


## -description


The D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration type contains values that identify quality levels for multisample patterns. 


## -syntax


````
typedef enum D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS { 
  D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN  = 0xffffffff,
  D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN    = 0xfffffffe
} D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS;
````


## -enum-fields




### -field D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN

The quality level value for standard multisample pattern. 


### -field D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN

The same number of samples as D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, except all the samples overlap the center of the pixel. 


## -remarks


The quality level value for standard multisample pattern is D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN. To expose support for the standard multisample pattern for a given sample count, the driver must expose at least one standard quality level through its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a> function. The D3D runtime can then use the D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN value. If hardware vendors have no proprietary sample patterns that they want to expose and just have the standard pattern, they can just implement the standard pattern for both quality level 0 as well as quality level D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN. In this situation, the driver's <b>CheckMultisampleQualityLevels</b> function would return a pointer to 1 in the <i>pNumQualityLevels</i> parameter. Applications can then request quality level 0 or D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, and both quality levels provide the same behavior.

For every sample count where D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN is supported, a sibling pattern (D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN) must be supported. D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN has the same number of samples as D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, except all the samples overlap the center of the pixel.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkmultisamplequalitylevels.md">CheckMultisampleQualityLevels</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

