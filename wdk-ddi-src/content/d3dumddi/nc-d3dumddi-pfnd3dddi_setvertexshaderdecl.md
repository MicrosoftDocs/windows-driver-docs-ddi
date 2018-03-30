---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERDECL
title: PFND3DDDI_SETVERTEXSHADERDECL
author: windows-driver-content
description: The SetVertexShaderDecl function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.
old-location: display\setvertexshaderdecl.htm
old-project: display
ms.assetid: 6387d632-78e2-4594-a58a-b11b2e831cc0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETVERTEXSHADERDECL, SetVertexShaderDecl, SetVertexShaderDecl callback function [Display Devices], UserModeDisplayDriver_Functions_83e6bdef-65e0-4357-aa4c-51e20cbeb6d5.xml, d3dumddi/SetVertexShaderDecl, display.setvertexshaderdecl
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	SetVertexShaderDecl
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETVERTEXSHADERDECL callback


## -description


The <i>SetVertexShaderDecl</i> function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param Arg1








#### - hShaderHandle [in]

 A handle to the vertex shader declaration object.


## -returns



<i>SetVertexShaderDecl</i> returns S_OK or an appropriate error result if the vertex shader declaration is not successfully set.




## -remarks



After setting the vertex shader declaration, all of the drawing operations use that declaration until another declaration is selected.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

