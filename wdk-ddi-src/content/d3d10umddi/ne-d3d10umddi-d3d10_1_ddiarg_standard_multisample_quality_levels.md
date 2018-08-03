---
UID: NE:d3d10umddi.D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
title: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
author: windows-driver-content
description: The D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration type contains values that identify quality levels for multisample patterns.
old-location: display\d3d10_1_ddiarg_standard_multisample_quality_levels.htm
tech.root: display
ms.assetid: 47c285fa-f53a-4e35-ad66-bf14dfc9f80e
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN, D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS, D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration [Display Devices], UMDisplayDriver_Dx10param_Structs_b617a227-3358-4b23-918f-9603c8fed13e.xml, d3d10umddi/D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN, d3d10umddi/D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, d3d10umddi/D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS, display.d3d10_1_ddiarg_standard_multisample_quality_levels
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
product:
- Windows
targetos: Windows
req.typenames: D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS
---

# D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration


## -description


The D3D10_1_DDIARG_STANDARD_MULTISAMPLE_QUALITY_LEVELS enumeration type contains values that identify quality levels for multisample patterns. 


## -enum-fields




### -field D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN

The quality level value for standard multisample pattern. 


### -field D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN

The same number of samples as D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, except all the samples overlap the center of the pixel. 


## -remarks



The quality level value for standard multisample pattern is D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN. To expose support for the standard multisample pattern for a given sample count, the driver must expose at least one standard quality level through its <a href="https://msdn.microsoft.com/2b6a0ab8-f197-48c3-baf2-305b77b7e8b5">CheckMultisampleQualityLevels</a> function. The D3D runtime can then use the D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN value. If hardware vendors have no proprietary sample patterns that they want to expose and just have the standard pattern, they can just implement the standard pattern for both quality level 0 as well as quality level D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN. In this situation, the driver's <b>CheckMultisampleQualityLevels</b> function would return a pointer to 1 in the <i>pNumQualityLevels</i> parameter. Applications can then request quality level 0 or D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, and both quality levels provide the same behavior.

For every sample count where D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN is supported, a sibling pattern (D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN) must be supported. D3D10_1_DDIARG_CENTER_MULTISAMPLE_PATTERN has the same number of samples as D3D10_1_DDIARG_STANDARD_MULTISAMPLE_PATTERN, except all the samples overlap the center of the pixel.




## -see-also




<a href="https://msdn.microsoft.com/2b6a0ab8-f197-48c3-baf2-305b77b7e8b5">CheckMultisampleQualityLevels</a>
 

 

