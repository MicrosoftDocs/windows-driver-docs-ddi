---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE
title: PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE
author: windows-driver-content
description: The CalcPrivateTessellationShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.
old-location: display\calcprivatetessellationshadersize.htm
old-project: display
ms.assetid: 604d7475-4696-429e-a645-781931509bb6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivatetessellationshadersize, CalcPrivateTessellationShaderSize callback function [Display Devices], CalcPrivateTessellationShaderSize, PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE, PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE, d3d10umddi/CalcPrivateTessellationShaderSize, UserModeDisplayDriverDx11_Functions_a669f28f-b275-4265-b6ae-5c3526d81b46.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateTessellationShaderSize is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname:
-	CalcPrivateTessellationShaderSize
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE callback


## -description


The <b>CalcPrivateTessellationShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.


## -prototype


````
PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE CalcPrivateTessellationShaderSize;

SIZE_T APIENTRY CalcPrivateTessellationShaderSize(
  _In_       D3D10DDI_HDEVICE                       hDevice,
  _In_ const UINT                                   *pCode,
  _In_ const D3D11DDIARG_TESSELLATION_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *pShaderCode



### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCode [in]

 An array of CONST UINT tokens that form the hull-shader code or domain-shader code.


#### - pSignatures [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tessellation_io_signatures.md">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the hull or domain shader's signature.


## -returns


<b>CalcPrivateTessellationShaderSize</b> returns the size of the memory region that the driver requires to create a hull or domain shader.



## -remarks


The Direct3D runtime calls the driver's <b>CalcPrivateTessellationShaderSize</b> function to calculate the size of the memory region for a hull or domain shader. This is similar to the way that the Direct3D runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a> function to calculate the size of the memory region for a pixel, vertex, or geometry shader (that is, a geometry shader without stream output).



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tessellation_io_signatures.md">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

