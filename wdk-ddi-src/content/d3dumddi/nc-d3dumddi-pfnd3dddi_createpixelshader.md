---
UID: NC:d3dumddi.PFND3DDDI_CREATEPIXELSHADER
title: PFND3DDDI_CREATEPIXELSHADER
author: windows-driver-content
description: The CreatePixelShader function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.
old-location: display\createpixelshader.htm
old-project: display
ms.assetid: b80a1823-6d91-440f-89e4-f7248579cc8f
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreatePixelShader, CreatePixelShader callback function [Display Devices], PFND3DDDI_CREATEPIXELSHADER, PFND3DDDI_CREATEPIXELSHADER callback, UserModeDisplayDriver_Functions_4e9d378f-d5aa-4b5d-9a66-ff2dd2f8fae8.xml, d3dumddi/CreatePixelShader, display.createpixelshader
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
-	CreatePixelShader
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEPIXELSHADER callback function


## -description


The <b>CreatePixelShader</b> function converts pixel shader code into a hardware-specific format and associates this code with a shader handle.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pCode [in]

 An array of CONST UINT tokens that make up the pixel shader code.


#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542952">D3DDDIARG_CREATEPIXELSHADER</a> structure that retrieves the shader handle that is associated with the pixel shader code that is specified by <b>pCode</b>.


## -returns



<b>CreatePixelShader</b> returns S_OK or an appropriate error result if the pixel shader code object is not successfully created.




## -remarks



For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542952">D3DDDIARG_CREATEPIXELSHADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

