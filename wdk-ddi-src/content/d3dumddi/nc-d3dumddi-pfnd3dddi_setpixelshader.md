---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADER
title: PFND3DDDI_SETPIXELSHADER
author: windows-driver-content
description: The SetPixelShader function sets a pixel shader to be used in all drawing operations.
old-location: display\setpixelshader.htm
old-project: display
ms.assetid: b7ffd96d-086e-445a-89cf-6f34a5b8a5d4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETPIXELSHADER, SetPixelShader, SetPixelShader callback function [Display Devices], UserModeDisplayDriver_Functions_dd7fa75c-0753-4786-b04a-2fdd0d0e7071.xml, d3dumddi/SetPixelShader, display.setpixelshader
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
-	SetPixelShader
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETPIXELSHADER callback


## -description


The <i>SetPixelShader</i> function sets a pixel shader to be used in all drawing operations. 


## -prototype


````
PFND3DDDI_SETPIXELSHADER SetPixelShader;

__checkReturn HRESULT APIENTRY SetPixelShader(
  _In_ HANDLE hDevice,
  _In_ HANDLE hShaderHandle
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param HANDLE








#### - hShaderHandle [in]

 A handle to the pixel shader code object.


## -returns



<i>SetPixelShader</i> returns S_OK or an appropriate error result if the pixel shader is not successfully set.




## -remarks



All subsequent drawing operations use the given shader until another is selected.

For user-mode display drivers that support pixel shaders before version 2.0, the Microsoft Direct3D runtime passes 0 in the <i>hShaderHandle</i> parameter to indicate a fixed-function pipeline. For user-mode display drivers that support pixel shader version 2.0 or later, the runtime converts Direct3D fixed-function pixel state to pixel shader version 2.0. For more information about fixed-function state, see <a href="https://msdn.microsoft.com/bc93d65e-ac16-470d-8c52-db8b1cc74456">Converting the Direct3D Fixed-Function State</a>.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPIXELSHADER callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

