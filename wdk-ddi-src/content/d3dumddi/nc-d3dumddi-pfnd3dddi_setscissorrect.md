---
UID: NC:d3dumddi.PFND3DDDI_SETSCISSORRECT
title: PFND3DDDI_SETSCISSORRECT
author: windows-driver-content
description: The SetScissorRect function marks a portion of a render target that rendering is confined to.
old-location: display\setscissorrect.htm
tech.root: display
ms.assetid: 779fd7ff-e4d6-45b4-8164-186e9cb89513
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETSCISSORRECT, PFND3DDDI_SETSCISSORRECT callback, SetScissorRect, SetScissorRect callback function [Display Devices], UserModeDisplayDriver_Functions_bd6b8a3d-d007-4272-9d43-f65c5da3959a.xml, d3dumddi/SetScissorRect, display.setscissorrect
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
-	SetScissorRect
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETSCISSORRECT callback function


## -description


The <i>SetScissorRect</i> function marks a portion of a render target that rendering is confined to. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pRect* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the 2-D portion of the render target to confine rendering to.


## -returns



<i>SetScissorRect</i> returns S_OK or an appropriate error result if the 2-D resource is not successfully marked.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

