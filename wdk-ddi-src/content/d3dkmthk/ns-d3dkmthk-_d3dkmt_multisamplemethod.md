---
UID: NS:d3dkmthk._D3DKMT_MULTISAMPLEMETHOD
title: "_D3DKMT_MULTISAMPLEMETHOD"
author: windows-driver-content
description: The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.
old-location: display\d3dkmt_multisamplemethod.htm
ms.assetid: 6cdc0665-61e6-4c13-9b15-46ce301febec
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_MULTISAMPLEMETHOD, D3DKMT_MULTISAMPLEMETHOD structure [Display Devices], OpenGL_Structs_0617065f-aa53-4b1a-9a3f-e135972d4852.xml, _D3DKMT_MULTISAMPLEMETHOD, d3dkmthk/D3DKMT_MULTISAMPLEMETHOD, display.d3dkmt_multisamplemethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_MULTISAMPLEMETHOD
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_MULTISAMPLEMETHOD
---

# _D3DKMT_MULTISAMPLEMETHOD structure


## -description


The D3DKMT_MULTISAMPLEMETHOD structure describes a multiple-sampling method.


## -struct-fields




### -field NumSamples

[out] The number of subpixels that are used in the multiple-sampling method (for example, 2 for 2x and 8 for 8x multiple-sampling).


### -field NumQualityLevels

[out] The upper bound on the quality range that is supported for the multiple-sampling method. The range extends from zero through the reported maximum quality setting.


### -field Reserved

[out] Reserved.


## -remarks



The driver can partition its quality levels for a given multiple-sampling method into as many increments as it requires, with the condition that each incremental step noticeably improves the quality of the presented image.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546975">D3DKMTGetMultisampleMethodList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548039">D3DKMT_GETMULTISAMPLEMETHODLIST</a>
 

 

