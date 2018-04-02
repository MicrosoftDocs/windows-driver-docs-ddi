---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONSTB
title: PFND3DDDI_SETPIXELSHADERCONSTB
author: windows-driver-content
description: The SetPixelShaderConstB function sets one or more pixel shader constant registers with Boolean values.
old-location: display\setpixelshaderconstb.htm
old-project: display
ms.assetid: 6f7c8932-9332-4ff2-89ab-2f9a66783326
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETPIXELSHADERCONSTB, SetPixelShaderConstB, SetPixelShaderConstB callback function [Display Devices], UserModeDisplayDriver_Functions_1f26c07c-fd24-4b1f-bc9d-23f6b8dae95f.xml, d3dumddi/SetPixelShaderConstB, display.setpixelshaderconstb
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
-	SetPixelShaderConstB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETPIXELSHADERCONSTB callback


## -description


The <i>SetPixelShaderConstB</i> function sets one or more pixel shader constant registers with Boolean values. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543329">D3DDDIARG_SETPIXELSHADERCONST</a> structure that describes how to set the pixel shader constant registers.


#### - pRegisters [in]

 A pointer to a buffer that contains BOOL values to copy.


## -returns



<i>SetPixelShaderConstB</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with Boolean values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543329">D3DDDIARG_SETPIXELSHADERCONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

