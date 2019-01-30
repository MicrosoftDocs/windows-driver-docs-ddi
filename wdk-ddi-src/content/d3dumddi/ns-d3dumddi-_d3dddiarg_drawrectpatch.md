---
UID: NS:d3dumddi._D3DDDIARG_DRAWRECTPATCH
title: _D3DDDIARG_DRAWRECTPATCH (d3dumddi.h)
description: The D3DDDIARG_DRAWRECTPATCH structure describes a rectangular patch to draw.
old-location: display\d3dddiarg_drawrectpatch.htm
tech.root: display
ms.assetid: 9e850fc5-a46a-4bd1-97a0-7ecc86102480
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DRAWRECTPATCH, D3DDDIARG_DRAWRECTPATCH structure [Display Devices], UMDisplayDriver_param_Structs_fc791424-dcfb-470b-a0d0-04534452707a.xml, _D3DDDIARG_DRAWRECTPATCH, d3dumddi/D3DDDIARG_DRAWRECTPATCH, display.d3dddiarg_drawrectpatch
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_DRAWRECTPATCH
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWRECTPATCH
---

# _D3DDDIARG_DRAWRECTPATCH structure


## -description


The D3DDDIARG_DRAWRECTPATCH structure describes a rectangular patch to draw. 


## -struct-fields




### -field Handle

[in] The handle to the patch surface.


## -remarks



The <b>Handle</b> member refers to the patch surface, so that the next time the patch surface is drawn, the Microsoft Direct3D runtime is not required to re-specify the D3DRECTPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information, which allows subsequent calls to the driver's <a href="https://msdn.microsoft.com/c0e3046c-f2af-4406-ac5a-c3e44f40b1fd">DrawRectPatch</a> function that use the same handle to run more efficiently.




## -see-also




<a href="https://msdn.microsoft.com/c0e3046c-f2af-4406-ac5a-c3e44f40b1fd">DrawRectPatch</a>
 

 

