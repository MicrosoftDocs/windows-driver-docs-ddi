---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERCONSTB
title: PFND3DDDI_SETVERTEXSHADERCONSTB (d3dumddi.h)
description: The SetVertexShaderConstB function sets one or more vertex shader constant registers with Boolean values.
old-location: display\setvertexshaderconstb.htm
tech.root: display
ms.assetid: 41ca823e-4370-4cba-9129-067e25a43a69
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETVERTEXSHADERCONSTB, PFND3DDDI_SETVERTEXSHADERCONSTB callback, SetVertexShaderConstB, SetVertexShaderConstB callback function [Display Devices], UserModeDisplayDriver_Functions_5151bd4a-84a4-43d3-a76e-de6f5808281d.xml, d3dumddi/SetVertexShaderConstB, display.setvertexshaderconstb
ms.topic: callback
f1_keywords:
 - "d3dumddi/SetVertexShaderConstB"
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
- SetVertexShaderConstB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETVERTEXSHADERCONSTB callback function


## -description


The <i>SetVertexShaderConstB</i> function sets one or more vertex shader constant registers with Boolean values.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a> structure that specifies how to set the vertex shader constant registers.

### -param Arg3

*pRegisters* [in]

A pointer to a buffer that contains BOOL values to copy.


## -returns



<i>SetVertexShaderConstB</i> returns S_OK or an appropriate error result if the vertex shader constant registers are not successfully set with Boolean values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

