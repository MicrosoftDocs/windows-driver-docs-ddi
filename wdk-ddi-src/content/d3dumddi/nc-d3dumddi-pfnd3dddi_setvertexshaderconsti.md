---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERCONSTI
title: PFND3DDDI_SETVERTEXSHADERCONSTI (d3dumddi.h)
description: The SetVertexShaderConstI function sets one or more vertex shader constant registers with integer values.
old-location: display\setvertexshaderconsti.htm
tech.root: display
ms.assetid: c245cfbd-0368-4a49-96a7-ac4cd14e2f5a
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETVERTEXSHADERCONSTI callback function"]
ms.keywords: PFND3DDDI_SETVERTEXSHADERCONSTI, PFND3DDDI_SETVERTEXSHADERCONSTI callback, SetVertexShaderConstI, SetVertexShaderConstI callback function [Display Devices], UserModeDisplayDriver_Functions_2cbf7e0b-a910-4072-a016-33a602fc0e95.xml, d3dumddi/SetVertexShaderConstI, display.setvertexshaderconsti
f1_keywords:
 - "d3dumddi/SetVertexShaderConstI"
 - "SetVertexShaderConstI"
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
- SetVertexShaderConstI
product: 
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3DDDI_SETVERTEXSHADERCONSTI callback function


## -description


The <i>SetVertexShaderConstI</i> function sets one or more vertex shader constant registers with integer values.


## -parameters




### -param hDevice 
[in]
A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a> structure that specifies how to set the vertex shader constant registers.

### -param Arg3

*pRegisters* [in]

A pointer to a buffer that contains INT values to copy.


## -returns



<i>SetVertexShaderConstI</i> returns S_OK or an appropriate error result if the vertex shader constant register is not successfully set with integer values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setvertexshaderconst">D3DDDIARG_SETVERTEXSHADERCONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

