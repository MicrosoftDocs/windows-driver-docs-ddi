---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERCONST
title: PFND3DDDI_SETVERTEXSHADERCONST (d3dumddi.h)
description: The SetVertexShaderConst function sets one or more vertex shader constant registers with floating-point values.
old-location: display\setvertexshaderconst.htm
tech.root: display
ms.assetid: 2dbde343-b10a-4357-a2b7-d6b1b1b868f2
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETVERTEXSHADERCONST, PFND3DDDI_SETVERTEXSHADERCONST callback, SetVertexShaderConst, SetVertexShaderConst callback function [Display Devices], UserModeDisplayDriver_Functions_473fa267-d7f2-47b7-bae8-3430d89dd632.xml, d3dumddi/SetVertexShaderConst, display.setvertexshaderconst
ms.topic: callback
f1_keywords:
 - "d3dumddi/SetVertexShaderConst"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- SetVertexShaderConst
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETVERTEXSHADERCONST callback function


## -description


The <i>SetVertexShaderConst</i> function sets one or more vertex shader constant registers with floating-point values.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a> structure that specifies how to set the vertex shader constant registers.

### -param Arg3

*pRegisters* [in]

A pointer to a buffer that contains the floating-point values to copy.


## -returns



<i>SetVertexShaderConst</i> returns S_OK or an appropriate error result if the vertex shader constant registers are not successfully set with floating-point values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

