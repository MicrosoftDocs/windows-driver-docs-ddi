---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONST
title: PFND3DDDI_SETPIXELSHADERCONST
author: windows-driver-content
description: The SetPixelShaderConst function sets one or more pixel shader constant registers with floating-point values.
old-location: display\setpixelshaderconst.htm
old-project: display
ms.assetid: 02710936-28df-4c8f-aa1e-bdff01155608
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3DDDI_SETPIXELSHADERCONST, SetPixelShaderConst, SetPixelShaderConst callback function [Display Devices], UserModeDisplayDriver_Functions_be972851-58a6-4f22-aae2-7948679b8bb7.xml, d3dumddi/SetPixelShaderConst, display.setpixelshaderconst
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	SetPixelShaderConst
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETPIXELSHADERCONST callback


## -description


The <i>SetPixelShaderConst</i> function sets one or more pixel shader constant registers with floating-point values. 


## -prototype


````
PFND3DDDI_SETPIXELSHADERCONST SetPixelShaderConst;

__checkReturn HRESULT APIENTRY SetPixelShaderConst(
  _In_       HANDLE                        hDevice,
  _In_ const D3DDDIARG_SETPIXELSHADERCONST *pData,
  _In_ const FLOAT                         *pRegisters
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setpixelshaderconst.md">D3DDDIARG_SETPIXELSHADERCONST</a> structure that describes how to set the pixel shader constant registers.


#### - pRegisters [in]

 A pointer to a buffer that contains 4-float vectors to copy.


## -returns



<i>SetPixelShaderConst</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with floating-point values.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setpixelshaderconst.md">D3DDDIARG_SETPIXELSHADERCONST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPIXELSHADERCONST callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

