---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The CalcPrivateGeometryShaderWithStreamOutput function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.
old-location: display\calcprivategeometryshaderwithstreamoutput.htm
tech.root: display
ms.assetid: 3e760b93-e859-4175-a24a-6bf3648db6db
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateGeometryShaderWithStreamOutput, CalcPrivateGeometryShaderWithStreamOutput callback function [Display Devices], PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT, PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback, UserModeDisplayDriverDx10_Functions_f35bbbad-dd97-4149-9bb6-75c6ea2b7cdc.xml, d3d10umddi/CalcPrivateGeometryShaderWithStreamOutput, display.calcprivategeometryshaderwithstreamoutput
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CalcPrivateGeometryShaderWithStreamOutput
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function


## -description


The <a href="https://msdn.microsoft.com/ba3f5a24-c608-42ca-bada-b126cb080f15">CalcPrivateGeometryShaderWithStreamOutput</a> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateGeometryShaderWithStreamOutput [in]


      A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541681">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 
     


#### - pSignatures [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns




<a href="https://msdn.microsoft.com/ba3f5a24-c608-42ca-bada-b126cb080f15">CalcPrivateGeometryShaderWithStreamOutput</a> returns the size of the memory region that the driver requires for creating a geometry shader with stream output.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541681">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 

