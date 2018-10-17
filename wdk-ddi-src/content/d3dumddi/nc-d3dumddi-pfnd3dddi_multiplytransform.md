---
UID: NC:d3dumddi.PFND3DDDI_MULTIPLYTRANSFORM
title: PFND3DDDI_MULTIPLYTRANSFORM
author: windows-driver-content
description: The MultiplyTransform function modifies the current transform.
old-location: display\multiplytransform.htm
tech.root: display
ms.assetid: 69d94062-5655-4d49-a116-7fa7e2b51a91
ms.date: 5/10/2018
ms.keywords: MultiplyTransform, MultiplyTransform callback function [Display Devices], PFND3DDDI_MULTIPLYTRANSFORM, PFND3DDDI_MULTIPLYTRANSFORM callback, UserModeDisplayDriver_Functions_4058eef2-8ccd-46e2-ad8d-fd0905811651.xml, d3dumddi/MultiplyTransform, display.multiplytransform
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	MultiplyTransform
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_MULTIPLYTRANSFORM callback function


## -description


The <i>MultiplyTransform</i> function modifies the current transform.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543221">D3DDDIARG_MULTIPLYTRANSFORM</a> structure that describes how to modify the current transform.


## -returns



<i>MultiplyTransform</i> returns S_OK or an appropriate error result if the transform is not successfully modified.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543221">D3DDDIARG_MULTIPLYTRANSFORM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

