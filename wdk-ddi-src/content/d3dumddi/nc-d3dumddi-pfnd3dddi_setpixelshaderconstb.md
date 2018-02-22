---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONSTB
title: PFND3DDDI_SETPIXELSHADERCONSTB
author: windows-driver-content
description: The SetPixelShaderConstB function sets one or more pixel shader constant registers with Boolean values.
old-location: display\setpixelshaderconstb.htm
old-project: display
ms.assetid: 6f7c8932-9332-4ff2-89ab-2f9a66783326
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.setpixelshaderconstb, SetPixelShaderConstB callback function [Display Devices], SetPixelShaderConstB, PFND3DDDI_SETPIXELSHADERCONSTB, PFND3DDDI_SETPIXELSHADERCONSTB, d3dumddi/SetPixelShaderConstB, UserModeDisplayDriver_Functions_1f26c07c-fd24-4b1f-bc9d-23f6b8dae95f.xml
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
-	SetPixelShaderConstB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETPIXELSHADERCONSTB callback


## -description


The <i>SetPixelShaderConstB</i> function sets one or more pixel shader constant registers with Boolean values. 


## -prototype


````
PFND3DDDI_SETPIXELSHADERCONSTB SetPixelShaderConstB;

__checkReturn HRESULT APIENTRY SetPixelShaderConstB(
  _In_       HANDLE                         hDevice,
  _In_ const D3DDDIARG_SETPIXELSHADERCONSTB *pData,
  _In_ const BOOL                           *pRegisters
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

 A pointer to a buffer that contains BOOL values to copy.


## -returns



<i>SetPixelShaderConstB</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with Boolean values.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setpixelshaderconst.md">D3DDDIARG_SETPIXELSHADERCONST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPIXELSHADERCONSTB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

