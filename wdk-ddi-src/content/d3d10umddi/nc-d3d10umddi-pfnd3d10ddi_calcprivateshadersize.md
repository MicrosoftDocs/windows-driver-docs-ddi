---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERSIZE
title: PFND3D10DDI_CALCPRIVATESHADERSIZE
author: windows-driver-content
description: The CalcPrivateShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.
old-location: display\calcprivateshadersize.htm
old-project: display
ms.assetid: 76cdddb0-b927-4547-ae1d-f5105905633b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivateshadersize, CalcPrivateShaderSize callback function [Display Devices], CalcPrivateShaderSize, PFND3D10DDI_CALCPRIVATESHADERSIZE, PFND3D10DDI_CALCPRIVATESHADERSIZE, d3d10umddi/CalcPrivateShaderSize, UserModeDisplayDriverDx10_Functions_32a6a3cc-1a0d-4a20-a985-0e0e50daa914.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
apiname:
-	CalcPrivateShaderSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CALCPRIVATESHADERSIZE callback


## -description


The <b>CalcPrivateShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader.


## -prototype


````
PFND3D10DDI_CALCPRIVATESHADERSIZE CalcPrivateShaderSize;

SIZE_T APIENTRY CalcPrivateShaderSize(
   D3D10DDI_HDEVICE                           hDevice,
   __in_ecount(pCode[1]) CONST UINT           *pCode,
   __in CONST D3D10DDIARG_STAGE_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *pShaderCode


### -param *








#### - hDevice

 [in] A handle to the display device (graphics context).


#### - pCode


      [in] An array of CONST UINT tokens that make up the shader code.
     


#### - pSignatures

 [in] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



<i>CalcPrivateShaderSize</i> returns the size of the memory region that the driver requires for creating a shader.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stage_io_signatures.md">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATESHADERSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

